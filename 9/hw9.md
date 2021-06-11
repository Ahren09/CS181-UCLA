# Homework 9

Name: Yiqiao Jin  
UID: 305107551

## 1 
$L$ is NOT a finite state language. We prove by contradiction using the **Pumping Lemma**.

Suppose $L$ is an FSL. There exists an integer $p$ (the pumping length), such that for all $s \in L$ $|s| \ge p$, there exists $x, y, z \in \Sigma^*$, such that $s=xyz$, and
- $|xy| \le p$
- $|y| \ge 1$
- For all $p \ge 0: xy^pz \in L$

Consider the string $s=0^{(p+1)}10^p10^{(p-1)}1...10^210^1$. According to the **Pumping Lemma**, the substring $xy$ must have length no greater than $p$. So $xy$ is contained within the prefix $0^{(p+1)}$, and $y$ must be all $0$'s. Thus $y$ is a consecutive series of $0$'s that is one of $0^p, 0^{(p-1)}, ... 0^2, 0^1$.

Using the **Pumping Lemma**, we can pump down on $s$ to get $s'=xy^0z=xz$. If $s \in L$, we should also have $s' \in L$. But no matter what the length of $y$ is, the first run of $0$'s that starts with $x$ must have a length that falls in the range $[1, p]$ (one of $0^p, 0^{(p-1)}, ... 0^2, 0^1$).

Since all the runs with length 1 up to $p$ are already present in the later part of the string, pumping down on $s$ must yield another run of length within the range $[1, p]$, which becomes a duplicate run of that length. Thus, $s' \notin L$. This contradicts the **Pumping Lemma**.

Therefore, $L$ is NOT a finite state language.