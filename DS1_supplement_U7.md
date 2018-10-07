<style scoped> @import url("rmd_doc_suffix.css"); </style>
# DS1 Course Supplemental Resources

## Unit 7: Introduction to Machine Learning

### 7.3: Detecting Tumors

If you follow along with the videos, you'll find that in part 4.7, Detecting Tumors, the images are rotated 90&deg; compared to the previous healthy MRI scans.

If this bothers you, then you want to add a line of code to "rotate" the matrix.

```{r}
tumorMatrix <- as.matrix(tumor)
# "Rotate" the matrix to match the orientation
# of the healthy images
tumorMatrix <- t(apply(tumorMatrix, 2, rev))
# Then continue on following the video
tumorVector <- as.vector(tumorMatrix)
```

Note that I've replaced `=` with `<-`. `=` and `<-` are not identical and interchangeable. See the [Unit 2 supplemental](DS1_supplement_U2.md#assignops) for further explanation.

If you'd like to plot the healthy scan, tumor scan, healthy cluster, and tumor cluster matrices all together, you can set up base graphics to plot four images on one graph with `par()`.

```{r}
par(mfcol = c(2, 2))
image(healthyMatrix, 
      col = grey(seq(0, 1, length.out = 256)), 
      axes = FALSE)
image(tumorMatrix, 
      col = grey(seq(0, 1, length.out = 256)), 
      axes = FALSE)
image(healthyClusters, 
      col = rainbow(n = length(KMC$size)),
      axes = FALSE)
image(tumorClusters, 
      col = rainbow(n = length(KMC$size)),
      axes = FALSE)
par(mfcol = c(1, 1))
```

### Time Series

Many data sets are in the form of time series&mdash;data collected over time, with some sort of time stamp. Knowing [how to analyze and decompose time series](http://rpubs.com/tomhopper/354688) will be useful to nearly every data scientist, Six Sigma practitioner, and engineer. Unfortunately, time series is not covered in the DS1 course. Follow the link above for an introduction that may help you with the course.
