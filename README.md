# CP Note (C++ used)

## FYI

---

**Variable type**

```cpp
cout << typeid(var).name();
```

**Prototype function**

```cpp
void solve(int a, int b);
int main(){
	...
}
void solve(int a, int b){
	...
}
```

**Get single line input**

```cpp
getline(cin, input);
```

## Sorting and Search

---

**Linear search**

```cpp
for(int i=0; i<n; i++){
	if(arr[i] == search) isFound = true;
}
```

**Binary search**

```cpp
mid = 0;
ans = 0;
left = 0;
right = arr.length()-1;

while(left<=right and ans==0){
	mid = (left+right) / 2;
	if(search<arr[mid]) right = mid-1;
	else if(search>arr[mid]) left = mid+1;
	else ans = arr[mid];
}
```

**Bubble Sort**

```cpp
for(int i=0; i<n; i++){
	for(int j=i+1; j<n; j++){
		if(arr[j] < arr[i]){
			temp = arr[i]
			arr[i] = arr[j]
			arr[j] = temp
		}
	}
}
```

**Selection Sort**

```cpp
for(int i=0; i<n; i++){
	smallest = 0;
	idx = i;

	//find smallest value
	for(int j=i+1; j<n; j++){
		if(arr[j] < smallest){
			smallest = arr[j];
			idx = j;  //save the index
		}
		temp = arr[i];
		arr[i] = arr[idx];
		arr[idx] = temp;
	}
}
```

**Sorting with Parameter Function**

```cpp
bool sc(int a, int b){
	if(a%b != 0) return true;
	else return false;

int main(){
	sort(arr, arr+n, sc);
}
```

## STRING

---

**Uppercase and lowercase**

```cpp
//to check
isupper(c)
islower(c)
//to convert
toupper(c)
tolower(c)
```

**Convert string to integer**

```cpp
string s = s**toi**(i);
```

**For each string characters**

```cpp
for(char c : str){
	...
}
```

## ARRAY

---

**Array summary**

```cpp
accumulate(arr, arr+arrLength, sum)
```

**Fill array**

```cpp
#include <cstring>
memset(arr, 0, sizeof(arr))
```

**Sort array ascending/descending**

```cpp
#include <algorithm>
sort(arr, arr+n); //ascending
sort(arr, arr+n, greater<int>()); //descending
sort(arr, arr+n, greater<double,int>()); //descending (pair)
```

**How many element types in array**

```cpp
int count = 0;
bool isUnique = true

for(int i=0; i<n; i++){
	for(int j=i+1; j<n; j++){
		if(arr[i] == arr[j]){
			isUnique = false;  //same element detected
			break;
	}
	
	if(isUnique) count++;
}
```

**Find an element in array**

```cpp
auto itr = find(begin(arr), end(arr), "search");  //return the address as itr, if "search" found, stop at it address then

if(itr != end(arr)) foundAtIndex = null;  //has been search till the end
else foundAtIndex = distance(arr, itr) 
```

**Check all of the array element**

```cpp
#include <algorithm>
if(all_of(begin(arr), end(arr), [](bool b){return b==true};)){
	isAllTrue = true;
}
```

**Permutation**

```cpp
#include <algorithm>
next_permutation(begin(arr), end(arr));
```

## FUNCTION

---

**Reverse number**

```cpp
rev = 0
while(num>0){
	rev = (rev*10) + (num%10);
	num /= 10;
}
```

**Prime number**

```cpp
int n; //angka yang dicek
bool isPrime = true;

for(int i=2; i*i<=n; i++){
	if(n/i == 0){
		isPrime = false;
		break;
	}
}

if(isPrime) cout << "Prime";
else cout << "Not Prime";
```

**Check its decimal or not**

```cpp
#include <cmath>
if(i/3 == floor(i/3)) isDecimal = false;
```

**Determine its a perfect square**

```cpp
temp = round(sqrt(i));
if(temp*temp == i) isPerfect = true;
```

**Euclid Method**

```cpp
int euclid(int a, int b){
	if(b==0) return a;
		else return euclid(b, %b);
}
```