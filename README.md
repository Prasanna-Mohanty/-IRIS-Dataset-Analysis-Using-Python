---


---

<p><strong>IRIS Data Set Analysis Using Python.</strong><br>
<strong>About the Dataset.</strong><br>
The Iris flower data set or Fisher’s Iris data set is a multivariate data set introduced by the British statistician and biologist Ronald Fisher in his 1936 paper, The use of multiple measurements in taxonomic problems, as an example of linear discriminant analysis.<br>
The Dataset consist of three iris species with 50 samples each as well as some properties about each flower. One flower species is linearly separable from the other two, but the other two are not linearly separable from each other.<br>
The columns in this dataset are:<br>
Id<br>
SepalLengthCm<br>
SepalWidthCm<br>
PetalLengthCm<br>
PetalWidthCm<br>
Species<br>
<img src="https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Machine+Learning+R/iris-machinelearning.png" alt="Image result for IRIS Dataset pictures"></p>
<p>Below Libraries are used</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Importing the libraries</span>
<span class="token keyword">import</span> numpy <span class="token keyword">as</span> np
<span class="token keyword">import</span> seaborn <span class="token keyword">as</span> sns
<span class="token keyword">import</span> matplotlib<span class="token punctuation">.</span>pyplot <span class="token keyword">as</span> plt
sns<span class="token punctuation">.</span><span class="token builtin">set</span><span class="token punctuation">(</span>color_codes<span class="token operator">=</span><span class="token boolean">True</span><span class="token punctuation">)</span>
<span class="token keyword">import</span> pandas <span class="token keyword">as</span> pd
<span class="token operator">%</span>matplotlib inline

</code></pre>
<p>Importing the Iris.csv file using Panda Library. First Five rows are displayed using dataset.head command.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Importing the dataset</span>
dataset <span class="token operator">=</span> pd<span class="token punctuation">.</span>read_csv<span class="token punctuation">(</span><span class="token string">'Iris.csv'</span><span class="token punctuation">)</span>
dataset<span class="token punctuation">.</span>head<span class="token punctuation">(</span><span class="token punctuation">)</span>

</code></pre>
<div>
<table class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>Id</th>
      <th>SepalLengthCm</th>
      <th>SepalWidthCm</th>
      <th>PetalLengthCm</th>
      <th>PetalWidthCm</th>
      <th>Species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>5.1</td>
      <td>3.5</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>4.9</td>
      <td>3.0</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>4.7</td>
      <td>3.2</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>4.6</td>
      <td>3.1</td>
      <td>1.5</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>5.0</td>
      <td>3.6</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
  </tbody>
</table>
</div>
<p>Below command will display number of Rows and Columns in the Table.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># shape Of the Data Set</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>dataset<span class="token punctuation">.</span>shape<span class="token punctuation">)</span>

</code></pre>
<pre><code>(150, 6)
</code></pre>
<p>Determining Minimum , Maximum, Mean , Median and Standard Deviation …</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Determining Minimum Value of each Column.</span>
dataset<span class="token punctuation">.</span><span class="token builtin">min</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<pre><code>Id                         1
SepalLengthCm            4.3
SepalWidthCm               2
PetalLengthCm              1
PetalWidthCm             0.1
Species          Iris-setosa
dtype: object
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Determining Maximum Value of each Column.</span>
dataset<span class="token punctuation">.</span><span class="token builtin">max</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<pre><code>Id                          150
SepalLengthCm               7.9
SepalWidthCm                4.4
PetalLengthCm               6.9
PetalWidthCm                2.5
Species          Iris-virginica
dtype: object
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Determining Mean Value of each Column.</span>
dataset<span class="token punctuation">.</span>mean<span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<pre><code>Id               75.500000
SepalLengthCm     5.843333
SepalWidthCm      3.054000
PetalLengthCm     3.758667
PetalWidthCm      1.198667
dtype: float64
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Determining Median Value of each Column.</span>
dataset<span class="token punctuation">.</span>median<span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<pre><code>Id               75.50
SepalLengthCm     5.80
SepalWidthCm      3.00
PetalLengthCm     4.35
PetalWidthCm      1.30
dtype: float64
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Determining Standard Deviation of each Column.</span>
dataset<span class="token punctuation">.</span>std<span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<pre><code>Id               43.445368
SepalLengthCm     0.828066
SepalWidthCm      0.433594
PetalLengthCm     1.764420
PetalWidthCm      0.763161
dtype: float64
</code></pre>
<p>Dropping the ID Column since there is no significance of this column.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment">#drop Id column</span>
dataset <span class="token operator">=</span> dataset<span class="token punctuation">.</span>drop<span class="token punctuation">(</span><span class="token string">'Id'</span><span class="token punctuation">,</span>axis<span class="token operator">=</span><span class="token number">1</span><span class="token punctuation">)</span>
dataset<span class="token punctuation">.</span>head<span class="token punctuation">(</span><span class="token punctuation">)</span>

</code></pre>
<div>
<table class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>SepalLengthCm</th>
      <th>SepalWidthCm</th>
      <th>PetalLengthCm</th>
      <th>PetalWidthCm</th>
      <th>Species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>3.5</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>3.0</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>3.2</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.6</td>
      <td>3.1</td>
      <td>1.5</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>3.6</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>Iris-setosa</td>
    </tr>
  </tbody>
</table>
</div>
<p>Displaying additional information.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># more info on the data</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>dataset<span class="token punctuation">.</span>info<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>&lt;class 'pandas.core.frame.DataFrame'&gt;
RangeIndex: 150 entries, 0 to 149
Data columns (total 5 columns):
SepalLengthCm    150 non-null float64
SepalWidthCm     150 non-null float64
PetalLengthCm    150 non-null float64
PetalWidthCm     150 non-null float64
Species          150 non-null object
dtypes: float64(4), object(1)
memory usage: 5.9+ KB
None
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># descriptions</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>dataset<span class="token punctuation">.</span>describe<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>       SepalLengthCm  SepalWidthCm  PetalLengthCm  PetalWidthCm
count     150.000000    150.000000     150.000000    150.000000
mean        5.843333      3.054000       3.758667      1.198667
std         0.828066      0.433594       1.764420      0.763161
min         4.300000      2.000000       1.000000      0.100000
25%         5.100000      2.800000       1.600000      0.300000
50%         5.800000      3.000000       4.350000      1.300000
75%         6.400000      3.300000       5.100000      1.800000
max         7.900000      4.400000       6.900000      2.500000
</code></pre>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># class distribution</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>dataset<span class="token punctuation">.</span>groupby<span class="token punctuation">(</span><span class="token string">'Species'</span><span class="token punctuation">)</span><span class="token punctuation">.</span>size<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>Species
Iris-setosa        50
Iris-versicolor    50
Iris-virginica     50
dtype: int64
</code></pre>
<p>Displaying the details by using Box and Whisker Plots</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># box and whisker plots</span>
dataset<span class="token punctuation">.</span>plot<span class="token punctuation">(</span>kind<span class="token operator">=</span><span class="token string">'box'</span><span class="token punctuation">,</span> sharex<span class="token operator">=</span><span class="token boolean">False</span><span class="token punctuation">,</span> sharey<span class="token operator">=</span><span class="token boolean">False</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f9bb3e88198&gt;
</code></pre>
<p><img src="output_12_1.png" alt="png"></p>
<p>Histogram Pictorial presentation of the data set.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># histograms</span>
dataset<span class="token punctuation">.</span>hist<span class="token punctuation">(</span>edgecolor<span class="token operator">=</span><span class="token string">'black'</span><span class="token punctuation">,</span> linewidth<span class="token operator">=</span><span class="token number">1.2</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>array([[&lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3bee320&gt;,
        &lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3bbe358&gt;],
       [&lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3b60518&gt;,
        &lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3b04668&gt;]],
      dtype=object)
</code></pre>
<p><img src="output_13_1.png" alt="png"></p>
<p>boxplot on each feature split out by species</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># boxplot on each feature split out by species</span>
dataset<span class="token punctuation">.</span>boxplot<span class="token punctuation">(</span>by<span class="token operator">=</span><span class="token string">"Species"</span><span class="token punctuation">,</span>figsize<span class="token operator">=</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">,</span><span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>array([[&lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3a94160&gt;,
        &lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3abcd68&gt;],
       [&lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb3a65048&gt;,
        &lt;matplotlib.axes._subplots.AxesSubplot object at 0x7f9bb37c62e8&gt;]],
      dtype=object)
</code></pre>
<p><img src="output_14_1.png" alt="png"></p>
<p>violin plots on petal-length for each species</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># violinplots on petal-length for each species</span>
sns<span class="token punctuation">.</span>violinplot<span class="token punctuation">(</span>data<span class="token operator">=</span>dataset<span class="token punctuation">,</span>x<span class="token operator">=</span><span class="token string">"Species"</span><span class="token punctuation">,</span> y<span class="token operator">=</span><span class="token string">"PetalLengthCm"</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>/home/nbuser/anaconda3_420/lib/python3.5/site-packages/scipy/stats/stats.py:1713: FutureWarning: Using a non-tuple sequence for multidimensional indexing is deprecated; use `arr[tuple(seq)]` instead of `arr[seq]`. In the future this will be interpreted as an array index, `arr[np.array(seq)]`, which will result either in an error or a different result.
  return np.add.reduce(sorted[indexer] * weights, axis=axis) / sumval





&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f9bb2ff0860&gt;
</code></pre>
<p><img src="output_15_2.png" alt="png"></p>
<p>scatter plot matrix</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">from</span> pandas<span class="token punctuation">.</span>tools<span class="token punctuation">.</span>plotting <span class="token keyword">import</span> scatter_matrix
<span class="token comment"># scatter plot matrix</span>
scatter_matrix<span class="token punctuation">(</span>dataset<span class="token punctuation">,</span>figsize<span class="token operator">=</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">,</span><span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">)</span>
plt<span class="token punctuation">.</span>show<span class="token punctuation">(</span><span class="token punctuation">)</span>


</code></pre>
<p><img src="output_16_0.png" alt="png"></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Using seaborn pairplot to see the bivariate relation between each pair of features</span>
sns<span class="token punctuation">.</span>pairplot<span class="token punctuation">(</span>dataset<span class="token punctuation">,</span> hue<span class="token operator">=</span><span class="token string">"Species"</span><span class="token punctuation">)</span>

</code></pre>
<pre><code>&lt;seaborn.axisgrid.PairGrid at 0x7f9bb2fdb6d8&gt;
</code></pre>
<p><img src="output_17_1.png" alt="png"></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># updating the diagonal elements in a pairplot to show a kde</span>
sns<span class="token punctuation">.</span>pairplot<span class="token punctuation">(</span>dataset<span class="token punctuation">,</span> hue<span class="token operator">=</span><span class="token string">"Species"</span><span class="token punctuation">,</span>diag_kind<span class="token operator">=</span><span class="token string">"kde"</span><span class="token punctuation">)</span>


</code></pre>
<pre><code>/home/nbuser/anaconda3_420/lib/python3.5/site-packages/scipy/stats/stats.py:1713: FutureWarning: Using a non-tuple sequence for multidimensional indexing is deprecated; use `arr[tuple(seq)]` instead of `arr[seq]`. In the future this will be interpreted as an array index, `arr[np.array(seq)]`, which will result either in an error or a different result.
  return np.add.reduce(sorted[indexer] * weights, axis=axis) / sumval





&lt;seaborn.axisgrid.PairGrid at 0x7f9bb1fa2128&gt;
</code></pre>
<p><img src="output_18_2.png" alt="png"></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Importing metrics for evaluation</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> confusion_matrix
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> classification_report

</code></pre>
<p>Separating the data into dependent and independent variables.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Seperating the data into dependent and independent variables</span>
X <span class="token operator">=</span> dataset<span class="token punctuation">.</span>iloc<span class="token punctuation">[</span><span class="token punctuation">:</span><span class="token punctuation">,</span> <span class="token punctuation">:</span><span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">.</span>values
y <span class="token operator">=</span> dataset<span class="token punctuation">.</span>iloc<span class="token punctuation">[</span><span class="token punctuation">:</span><span class="token punctuation">,</span> <span class="token operator">-</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">.</span>values

Splitting the data <span class="token builtin">set</span> into training <span class="token operator">and</span> test sets<span class="token punctuation">.</span>

<span class="token comment"># Splitting the dataset into the Training set and Test set</span>
<span class="token comment">#from sklearn.cross_validation import train_test_split</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>model_selection <span class="token keyword">import</span> train_test_split
X_train<span class="token punctuation">,</span> X_test<span class="token punctuation">,</span> y_train<span class="token punctuation">,</span> y_test <span class="token operator">=</span> train_test_split<span class="token punctuation">(</span>X<span class="token punctuation">,</span> y<span class="token punctuation">,</span> test_size <span class="token operator">=</span> <span class="token number">0.2</span><span class="token punctuation">,</span> random_state <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">)</span>

</code></pre>
<p>Fitting and predicting the data sets into Logistic Regression model and finding out the accuracy level.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># LogisticRegression</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>linear_model <span class="token keyword">import</span> LogisticRegression
classifier1 <span class="token operator">=</span> LogisticRegression<span class="token punctuation">(</span><span class="token punctuation">)</span>
classifier1<span class="token punctuation">.</span>fit<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span>

y_pred <span class="token operator">=</span> classifier1<span class="token punctuation">.</span>predict<span class="token punctuation">(</span>X_test<span class="token punctuation">)</span>

<span class="token comment"># Summary of the predictions made by the classifier</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>classification_report<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>confusion_matrix<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment"># Accuracy percentage on test dataset</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> accuracy_score
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on test dataset is'</span><span class="token punctuation">,</span><span class="token builtin">round</span><span class="token punctuation">(</span>accuracy_score<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span>y_pred<span class="token punctuation">)</span><span class="token operator">*</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment">#Accuracy Percentage on training dataset</span>
acc_log1 <span class="token operator">=</span> <span class="token builtin">round</span><span class="token punctuation">(</span>classifier1<span class="token punctuation">.</span>score<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on training dataset is'</span><span class="token punctuation">,</span>acc_log1<span class="token punctuation">)</span>
</code></pre>
<pre><code>                 precision    recall  f1-score   support

    Iris-setosa       1.00      1.00      1.00        11
Iris-versicolor       1.00      0.92      0.96        13
 Iris-virginica       0.86      1.00      0.92         6

    avg / total       0.97      0.97      0.97        30

[[11  0  0]
 [ 0 12  1]
 [ 0  0  6]]
accuracy percentage on test dataset is 96.67
accuracy percentage on training dataset is 93.33
</code></pre>
<p>Fitting and predicting the data sets into Naive Bayes model and finding out the accuracy level.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Naive Bayes</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>naive_bayes <span class="token keyword">import</span> GaussianNB
classifier2 <span class="token operator">=</span> GaussianNB<span class="token punctuation">(</span><span class="token punctuation">)</span>
classifier2<span class="token punctuation">.</span>fit<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span>

y_pred <span class="token operator">=</span> classifier2<span class="token punctuation">.</span>predict<span class="token punctuation">(</span>X_test<span class="token punctuation">)</span>

<span class="token comment"># Summary of the predictions made by the classifier</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>classification_report<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>confusion_matrix<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token comment"># Accuracy percentage on test dataset</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> accuracy_score
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on test dataset is'</span><span class="token punctuation">,</span><span class="token builtin">round</span><span class="token punctuation">(</span>accuracy_score<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span>y_pred<span class="token punctuation">)</span><span class="token operator">*</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token comment">#Accuracy Percentage on training dataset</span>
acc_log2 <span class="token operator">=</span> <span class="token builtin">round</span><span class="token punctuation">(</span>classifier2<span class="token punctuation">.</span>score<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on training dataset is'</span><span class="token punctuation">,</span>acc_log2<span class="token punctuation">)</span>

</code></pre>
<pre><code>                 precision    recall  f1-score   support

    Iris-setosa       1.00      1.00      1.00        11
Iris-versicolor       0.93      1.00      0.96        13
 Iris-virginica       1.00      0.83      0.91         6

    avg / total       0.97      0.97      0.97        30

[[11  0  0]
 [ 0 13  0]
 [ 0  1  5]]
accuracy percentage on test dataset is 96.67
accuracy percentage on training dataset is 95.0
</code></pre>
<p>Fitting and predicting the data sets into SVM model and finding out the accuracy level.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Support Vector Machine's </span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>svm <span class="token keyword">import</span> SVC

classifier3 <span class="token operator">=</span> SVC<span class="token punctuation">(</span><span class="token punctuation">)</span>
classifier3<span class="token punctuation">.</span>fit<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span>

y_pred <span class="token operator">=</span> classifier3<span class="token punctuation">.</span>predict<span class="token punctuation">(</span>X_test<span class="token punctuation">)</span>

<span class="token comment"># Summary of the predictions made by the classifier</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>classification_report<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>confusion_matrix<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment"># Accuracy Percentage on test dataset</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> accuracy_score
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on test dataset is'</span><span class="token punctuation">,</span><span class="token builtin">round</span><span class="token punctuation">(</span>accuracy_score<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span>y_pred<span class="token punctuation">)</span><span class="token operator">*</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment">#Accuracy Percentage on training dataset</span>
acc_log3 <span class="token operator">=</span> <span class="token builtin">round</span><span class="token punctuation">(</span>classifier3<span class="token punctuation">.</span>score<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on training dataset is'</span><span class="token punctuation">,</span>acc_log3<span class="token punctuation">)</span>

</code></pre>
<pre><code>                 precision    recall  f1-score   support

    Iris-setosa       1.00      1.00      1.00        11
Iris-versicolor       1.00      1.00      1.00        13
 Iris-virginica       1.00      1.00      1.00         6

    avg / total       1.00      1.00      1.00        30

[[11  0  0]
 [ 0 13  0]
 [ 0  0  6]]
accuracy percentage on test dataset is 100.0
accuracy percentage on training dataset is 97.5
</code></pre>
<p>Fitting and predicting the data sets into KNN model and finding out the accuracy level.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># K-Nearest Neighbours</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>neighbors <span class="token keyword">import</span> KNeighborsClassifier

classifier4 <span class="token operator">=</span> KNeighborsClassifier<span class="token punctuation">(</span>n_neighbors<span class="token operator">=</span><span class="token number">8</span><span class="token punctuation">)</span>
classifier4<span class="token punctuation">.</span>fit<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span>

y_pred <span class="token operator">=</span> classifier4<span class="token punctuation">.</span>predict<span class="token punctuation">(</span>X_test<span class="token punctuation">)</span>

<span class="token comment"># Summary of the predictions made by the classifier</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>classification_report<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>confusion_matrix<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment"># Accuracy Percentage on test dataset</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> accuracy_score
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on test dataset is'</span><span class="token punctuation">,</span><span class="token builtin">round</span><span class="token punctuation">(</span>accuracy_score<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span>y_pred<span class="token punctuation">)</span><span class="token operator">*</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment">#Accuracy Percentage on training dataset</span>
acc_log4 <span class="token operator">=</span> <span class="token builtin">round</span><span class="token punctuation">(</span>classifier4<span class="token punctuation">.</span>score<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on training dataset is'</span><span class="token punctuation">,</span>acc_log4<span class="token punctuation">)</span>
</code></pre>
<pre><code>                 precision    recall  f1-score   support

    Iris-setosa       1.00      1.00      1.00        11
Iris-versicolor       1.00      1.00      1.00        13
 Iris-virginica       1.00      1.00      1.00         6

    avg / total       1.00      1.00      1.00        30

[[11  0  0]
 [ 0 13  0]
 [ 0  0  6]]
accuracy percentage on test dataset is 100.0
accuracy percentage on training dataset is 96.67
</code></pre>
<p>Fitting and predicting the data sets into Decision Tree’s model and finding out the accuracy level.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token comment"># Decision Tree's</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>tree <span class="token keyword">import</span> DecisionTreeClassifier

classifier5 <span class="token operator">=</span> DecisionTreeClassifier<span class="token punctuation">(</span><span class="token punctuation">)</span>

classifier5<span class="token punctuation">.</span>fit<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span>

y_pred <span class="token operator">=</span> classifier5<span class="token punctuation">.</span>predict<span class="token punctuation">(</span>X_test<span class="token punctuation">)</span>

<span class="token comment"># Summary of the predictions made by the classifier</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>classification_report<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>confusion_matrix<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span> y_pred<span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token comment"># Accuracy Percentage on test dataset</span>
<span class="token keyword">from</span> sklearn<span class="token punctuation">.</span>metrics <span class="token keyword">import</span> accuracy_score
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on test dataset is'</span><span class="token punctuation">,</span><span class="token builtin">round</span><span class="token punctuation">(</span>accuracy_score<span class="token punctuation">(</span>y_test<span class="token punctuation">,</span>y_pred<span class="token punctuation">)</span><span class="token operator">*</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">)</span>
<span class="token comment">#Accuracy Percentage on training dataset</span>
acc_log5 <span class="token operator">=</span> <span class="token builtin">round</span><span class="token punctuation">(</span>classifier5<span class="token punctuation">.</span>score<span class="token punctuation">(</span>X_train<span class="token punctuation">,</span> y_train<span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span>
<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'accuracy percentage on training dataset is'</span><span class="token punctuation">,</span>acc_log5<span class="token punctuation">)</span>
</code></pre>
<pre><code>                 precision    recall  f1-score   support

    Iris-setosa       1.00      1.00      1.00        11
Iris-versicolor       1.00      1.00      1.00        13
 Iris-virginica       1.00      1.00      1.00         6

    avg / total       1.00      1.00      1.00        30

[[11  0  0]
 [ 0 13  0]
 [ 0  0  6]]
accuracy percentage on test dataset is 100.0
accuracy percentage on training dataset is 100.0
</code></pre>
<p>Determining which model is best fit for this Dataset.</p>
<pre class=" language-python"><code class="prism  language-python">models <span class="token operator">=</span> pd<span class="token punctuation">.</span>DataFrame<span class="token punctuation">(</span><span class="token punctuation">{</span>
    <span class="token string">'Model'</span><span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token string">'Logistic Regression'</span><span class="token punctuation">,</span> <span class="token string">'Naive Bayes'</span><span class="token punctuation">,</span> <span class="token string">'SVC'</span><span class="token punctuation">,</span><span class="token string">'KNN'</span><span class="token punctuation">,</span> 
              <span class="token string">'Decision Tree'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>
    <span class="token string">'Score'</span><span class="token punctuation">:</span> <span class="token punctuation">[</span>acc_log1<span class="token punctuation">,</span> acc_log2<span class="token punctuation">,</span> acc_log3<span class="token punctuation">,</span> 
              acc_log4<span class="token punctuation">,</span> acc_log5<span class="token punctuation">]</span><span class="token punctuation">}</span><span class="token punctuation">)</span>
models<span class="token punctuation">.</span>sort_values<span class="token punctuation">(</span>by<span class="token operator">=</span><span class="token string">'Score'</span><span class="token punctuation">,</span> ascending<span class="token operator">=</span><span class="token boolean">False</span><span class="token punctuation">)</span>
</code></pre>
<div>
<table class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>Model</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>Decision Tree</td>
      <td>100.00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>SVC</td>
      <td>97.50</td>
    </tr>
    <tr>
      <th>3</th>
      <td>KNN</td>
      <td>96.67</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Naive Bayes</td>
      <td>95.00</td>
    </tr>
    <tr>
      <th>0</th>
      <td>Logistic Regression</td>
      <td>93.33</td>
    </tr>
  </tbody>
</table>
</div>

