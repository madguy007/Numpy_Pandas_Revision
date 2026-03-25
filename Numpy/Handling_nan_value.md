## Handling NaN (np.isnan)
Key Point:

NaN != NaN → normal comparison fails
## Check NaN
import numpy as np

arr = np.array([1, 2, np.nan, 4])

np.isnan(arr)
 [False False  True False]
## Filter
arr[np.isnan(arr)]      # get NaN
arr[~np.isnan(arr)]     # remove NaN
## Replace NaN with mean
arr[np.isnan(arr)] = np.mean(arr[~np.isnan(arr)])
