# Codechef_starters_108_Div3

# Chess Pairing
<details>
<summary>Python</summary>

```python
t = int(input())
for _ in range(t):
    n, x = map(int, input().split())
    if 2 * x >= 2 * n:
        print(2 * x - 2 * n)
    else:
        print(0)
```
</details>

<details>
<summary>Cpp</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
	// your code goes here
	int t;
	cin >> t;
	while(t--) {
    	int n, x;
	    cin >> n >> x;
	    if (2 * x >= 2 * n)
	        cout << 2 * x - 2 * n << endl;
	    else
	        cout << 0 << endl;
	}
}
```
</details>


<details>
<summary>Java</summary>

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt();
        
        while (t-- > 0) {
            int n = scanner.nextInt();
            int x = scanner.nextInt();
            
            if (2 * x >= 2 * n) {
                System.out.println(2 * x - 2 * n);
            } else {
                System.out.println(0);
            }
        }
        
        scanner.close();
    }
}
```
</details>

<!-- Second Question -->
# Palindromic Prime Numbers

<details>
<summary>Python</summary>

```python
t = int(input())
for _ in range(t):
    n = int(input())
    if n >= 5:
        print("1", n-1)
    else:
        print("0", n)
```

</details>

<details>
<summary>Cpp</summary>
  
```cpp
#include <iostream>
using namespace std;

int main() {
	int t;
	cin >> t;
	while(t--) {
	    int n;
	    cin >> n;
	    if (n >= 5)
	        cout << "1 " << n-1 << endl;
	    else
	        cout << "0 " << n << endl;
	}
	return 0;
}
```

</details>
<!-- Java -->
<details>
<summary>Java</summary>

```Java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt();
        
        while (t-- > 0) {
            int n = scanner.nextInt();
            
            if (n >= 5) {
                System.out.println("1 " + (n-1));
            } else {
                System.out.println("0 " + n);
            }
        }
        
        scanner.close();
    }
}
```
</details>

# OR Permutation

<details>
<summary>Python</summary>

```python
t = int(input())
for _ in range(t):
    n = int(input())
    for i in range(n, 0, -1):
        print(i, end=" ")
    print()

```
</details>

<details>
<summary>Cpp</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--){
	    int n;
	    cin>>n;
	    for(int i=n;i>=1;i--){
	        cout<<i<<" ";
	    }
	    
	    cout<<endl;
	}
	return 0;
}
```
</details>

<details>
<summary>Java</summary>

```Java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt();

        while (t-- > 0) {
            int n = scanner.nextInt();
            for (int i = n; i >= 1; i--) {
                System.out.print(i + " ");
            }
            System.out.println();
        }
    }
}

```
</details>

# Maximal Expression

<details>
    <summary>Python Code</summary>

```python
t = int(input())
for _ in range(t):
    n, k = list(map(int, input().split()))
    K = min(n, k - 1)
    if K == 0:
        print(K)
        continue
    a = (n - K) % k
    b = (K // 2) + (K % 2)
    print(b + a // 2)

```
</details>


<details>
  	<summary>C++</summary>
  
```cpp
#include <iostream>
using namespace std;

int main() {
    int t;
    cin >> t;
    for (int i = 0; i < t; i++) {
        int n, k;
        cin >> n >> k;
        int K = min(n, k - 1);
        if (K == 0) {
            cout << K << endl;
            continue;
        }
        int a = (n - K) % k;
        int b = (K / 2) + (K % 2);
        cout << b + a / 2 << endl;
    }
    return 0;
}

```
</details>


<details>
	<summary>JAVA</summary>
  
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt();
        for (int i = 0; i < t; i++) {
            int n = scanner.nextInt();
            int k = scanner.nextInt();
            int K = Math.min(n, k - 1);
            if (K == 0) {
                System.out.println(K);
                continue;
            }
            int a = (n - K) % k;
            int b = (K / 2) + (K % 2);
            System.out.println(b + a / 2);
        }
    }
}
```
</details>

# Multiple Of 9

<details>
    <summary>Python Code</summary>

```python
t = int(input())
for _ in range(t):
    n = int(input())
    s = input()
    sum_val = 0
    q = 0
    
    for i in range(n):
        if s[i] == '?':
            q += 1
        else:
            sum_val += int(s[i])

    if s[0] == '?':
        print('1' + '0' * (q-1))
    elif sum_val % 9 != 0:
        print('1' * q)
    else:
        print('1' * (q-1) + '2')
```
</details>


<details>
  	<summary>C++</summary>
  
```cpp
#include <iostream>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--){
	    int n;
	    cin>>n;
	    string s;
	    cin>>s;
	    int sum=0,q=0;
	    for(int i=0;i<n;i++){
	        if(s[i]=='?') q++;
	        else{
	            sum+=(s[i]-'0');
	        }
	    }
	    if(s[0]=='?'){
	        cout<<'1';
	        for(int i=1;i<q;i++) cout<<'0';
	    }
	    else if(sum%9!=0){
	        for(int i=0;i<q;i++) cout<<'1';
	    }
	    else{
	        for(int i=0;i<q-1;i++) cout<<'1';
	        cout<<'2';
	    }
	    cout<<endl;
	}
	return 0;
}
```
</details>


<details>
	<summary>JAVA</summary>
  
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt();

        for (int k = 0; k < t; k++) {
            int n = scanner.nextInt();
            String s = scanner.next();
            int sum = 0;
            int q = 0;

            for (int i = 0; i < n; i++) {
                if (s.charAt(i) == '?') {
                    q++;
                } else {
                    sum += Character.getNumericValue(s.charAt(i));
                }
            }

            if (s.charAt(0) == '?') {
                System.out.print("1");
                for (int i = 1; i < q; i++) {
                    System.out.print("0");
                }
            } else if (sum % 9 != 0) {
                for (int i = 0; i < q; i++) {
                    System.out.print("1");
                }
            } else {
                for (int i = 0; i < q - 1; i++) {
                    System.out.print("1");
                }
                System.out.print("2");
            }

            System.out.println();
        }
    }
}
```
</details>
