# Codechef_starters_108_Div3

# Pending Assignments
<details>
<summary>Python</summary>

```python
t = int(input())
for _ in range(t):
    a, b, c = map(int, input().split())
    print("YES" if a * b <= 1440 * c else "NO")
```
</details>

<details>
<summary>Cpp</summary>

```cpp
#include <iostream>
using namespace std;

int main() {
	int t,a,b,c;
	cin>>t;
	while(t--)
	{
	    cin>>a>>b>>c;
	    cout<<(a*b<=1440*c?"YES":"NO")<<endl;
	}
	return 0;
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
        for (int i = 0; i < t; i++) {
            int a = scanner.nextInt();
            int b = scanner.nextInt();
            int c = scanner.nextInt();
            System.out.println(a * b <= 1440 * c ? "YES" : "NO");
        }
    }
}

```
</details>

<!-- Second Question -->
# Rock Paper Scissor

<details>
<summary>Python</summary>

```python
t = int(input())
for _ in range(t):
    n = int(input())
    A = input()
    B = input()
    
    counter1 = counter2 = 0
    
    for i in range(n):
        if (A[i] == 'R' and B[i] == 'P') or \
           (A[i] == 'S' and B[i] == 'R') or \
           (A[i] == 'P' and B[i] == 'S'):
            counter2 += 1
        elif (A[i] == 'R' and B[i] == 'S') or \
             (A[i] == 'P' and B[i] == 'R') or \
             (A[i] == 'S' and B[i] == 'P'):
            counter1 += 1

    num = 0
    if counter2 >= counter1:
        num = ((counter2 - counter1) // 2) + 1
        print(num)
    else:
        print(0)

```

</details>

<details>
<summary>Cpp</summary>
  
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;

        string A ;
        cin >> A ;
        string B ;
        cin>> B;

        int counter1 = 0, counter2 = 0;

        for (int i = 0; i < n; i++) {
            if ((A[i] == 'R' && B[i] == 'P') ||
            (A[i] == 'S' && B[i] == 'R') || 
            (A[i] == 'P' && B[i] == 'S'))
            {
                counter2 ++;
            }
            else if ((A[i] == 'R' && B[i] == 'S') ||
            (A[i] == 'P' && B[i] == 'R') ||
            (A[i] == 'S' && B[i] == 'P'))
            {
                counter1 ++;
            } 
            
        }

        int num = 0;
        if (counter2 >= counter1) {
            num = ((counter2 - counter1) / 2) + 1;
            cout << num << endl;
        } 
        else 
            cout << 0 << endl;
        
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
            String A = scanner.next();
            String B = scanner.next();

            int counter1 = 0, counter2 = 0;

            for (int i = 0; i < n; i++) {
                if ((A.charAt(i) == 'R' && B.charAt(i) == 'P') ||
                    (A.charAt(i) == 'S' && B.charAt(i) == 'R') ||
                    (A.charAt(i) == 'P' && B.charAt(i) == 'S')) {
                    counter2++;
                } else if ((A.charAt(i) == 'R' && B.charAt(i) == 'S') ||
                           (A.charAt(i) == 'P' && B.charAt(i) == 'R') ||
                           (A.charAt(i) == 'S' && B.charAt(i) == 'P')) {
                    counter1++;
                }
            }

            int num = 0;
            if (counter2 >= counter1) {
                num = ((counter2 - counter1) / 2) + 1;
                System.out.println(num);
            } else {
                System.out.println(0);
            }
        }
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
