<pre>
Assume you have an array A[N].
Now, consider a custom array arr[N],
where the value at the ith index represents the sum of elements from index 0 to i in array A, known as the 'prefix sum.'

Now, let's analyze the expression arr[r] - arr[l]:

\[arr[r] - arr[l] = \text{sum of elements from 0th to rth} - \text{sum of elements from 0th to lth} = \text{sum of elements from (l + 1)th to rth}.\]

However, the question requires the result to be inclusive of both l and r. Therefore, the corrected expression is \(arr[r] - arr[l - 1]\).

But, there's a caveat. What if \(l == 0\)?

If \(l == 0\), then \(l - 1\) becomes -1, causing \(arr[l - 1]\) to throw an error. To address this, when \(l == 0\), it implies the summation of all elements till index r. In this case, simply print \(arr[j]\).
</pre>
