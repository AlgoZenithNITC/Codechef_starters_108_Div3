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

# Fair Distribution

<details>
<summary>Python</summary>

```python
def solve():
    n = int(input())
    binary_string = input()

    if any(binary_string[i] == binary_string[i + 1] for i in range(n - 2, -1, -2)):
        print("NO")
    else:
        print("YES")


testcases = int(input())

for _ in range(testcases):
    solve()
    print()



```
</details>

<details>
<summary>Cpp</summary>

```cpp
#include <iostream>
#include <vector>
using namespace std;
void solve() {
    int n;
    cin >> n;


    string binaryString;
    cin >> binaryString;


    for (int i = n - 2; i >= 0; i -= 2) {
        if (binaryString[i] == binaryString[i + 1]) {
            cout << "NO";
            return;
        }
    }

    cout << "YES";
}

int main() {

    int testcases;
    cin >> testcases;
    while (testcases--) {
        solve();
        cout << endl;
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
    public static void solve() {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        String binaryString = scanner.next();

        for (int i = n - 2; i >= 0; i -= 2) {
            if (binaryString.charAt(i) == binaryString.charAt(i + 1)) {
                System.out.println("NO");
                return;
            }
        }

        System.out.println("YES");
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int testcases = scanner.nextInt();

        for (int t = 0; t < testcases; t++) {
            solve();
            System.out.println();
        }
    }
}


```
</details>

# Clan Expansion

<details>
    <summary>Python Code</summary>

```python
t = int(input())

for _ in range(t):
    n = int(input())
    arr = list(map(int, input().split()))
    D = {}
    
    for i in range(n):
        if arr[i] not in D:
            D[arr[i]] = [i]
        else:
            D[arr[i]].append(i)

    ans = [float('inf'), float('inf')]

    for i in range(1, n + 1):
        if i in D:
            L = D[i]
            if L:
                time = D[i][0]

                for j in range(1, len(L)):
                    bet = L[j] - L[j - 1] - 1
                    if bet:
                        time = max(bet // 2 + bet % 2, time)

                time = max(n - D[i][-1] - 1, time)

                if time < ans[0]:
                    ans = [time, i]

    print(ans[1], ans[0])


```
</details>


<details>
  	<summary>C++</summary>
  
```cpp
#include <iostream>
#include <vector>
#include <unordered_map>
#include <climits>

using namespace std;

int main() {
    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;

        vector<int> arr(n);
        unordered_map<int, vector<int>> D;

        for (int i = 0; i < n; i++) {
            cin >> arr[i];
            D[arr[i]].push_back(i);
        }

        vector<int> ans = {INT_MAX, INT_MAX};

        for (int i = 1; i <= n; i++) {
            if (D.find(i) != D.end()) {
                vector<int> L = D[i];
                if (!L.empty()) {
                    int time = D[i][0];

                    for (int j = 1; j < L.size(); j++) {
                        int bet = L[j] - L[j - 1] - 1;
                        if (bet) {
                            time = max(bet / 2 + bet % 2, time);
                        }
                    }

                    time = max(n - D[i].back() - 1, time);

                    if (time < ans[0]) {
                        ans = {time, i};
                    }
                }
            }
        }

        cout << ans[1] << " " << ans[0] << endl;
    }

    return 0;
}

```
</details>


<details>
	<summary>JAVA</summary>
  
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int t = scanner.nextInt();
        while (t-- > 0) {
            int n = scanner.nextInt();
            int[] arr = new int[n];
            Map<Integer, List<Integer>> D = new HashMap<>();

            for (int i = 0; i < n; i++) {
                arr[i] = scanner.nextInt();
                D.computeIfAbsent(arr[i], k -> new ArrayList<>()).add(i);
            }

            int[] ans = {Integer.MAX_VALUE, Integer.MAX_VALUE};

            for (int i = 1; i <= n; i++) {
                if (D.containsKey(i)) {
                    List<Integer> L = D.get(i);
                    if (!L.isEmpty()) {
                        int time = D.get(i).get(0);

                        for (int j = 1; j < L.size(); j++) {
                            int bet = L.get(j) - L.get(j - 1) - 1;
                            if (bet > 0) {
                                time = Math.max(bet / 2 + bet % 2, time);
                            }
                        }

                        time = Math.max(n - D.get(i).get(L.size() - 1) - 1, time);

                        if (time < ans[0]) {
                            ans[0] = time;
                            ans[1] = i;
                        }
                    }
                }
            }

            System.out.println(ans[1] + " " + ans[0]);
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
