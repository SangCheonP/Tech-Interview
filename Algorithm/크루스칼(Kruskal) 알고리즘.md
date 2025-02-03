## 크루스칼(Kruskal) 알고리즘
```
최소 스패닝 트리(MST, Minimum Spanning Tree)를 찾는 대표적인 알고리즘

* 비슷한 Prim 알고리즘도 있지만 -> PQ를 사용하기 때문에 간선이 많을 때 적합
```

<br>

### 📌 크루스칼 알고리즘이란?
- 간선 중심(Egde-based) 알고리즘: 최소 비용의 간선부터 선택하여 MST를 만듦.

- 유니온 파인드(Union-Find) 활용: 사이클이 생기지 않도록 관리.

- 시간 복잡도: 𝑂(𝐸 log 𝐸) (E: 간선 수)

<br>

### 📌 크루스칼 알고리즘의 핵심 개념

✅ 1. 간선 리스트 정렬
- 모든 간선을 비용 기준으로 오름차순 정렬.
- 가장 작은 비용부터 차례로 확인하면서 연결.

✅ 2. 유니온 파인드(Union-Find) 사용
- find(): 특정 노드의 최상위 부모(루트 노드)를 찾음 (경로 압축 최적화)
- union(): 두 노드를 같은 집합으로 합침 (랭크 기반 최적화)
- 사이클 발생 여부 체크: 두 노드가 이미 같은 집합이면 추가하지 않음.

✅ 3. MST가 완성되면 종료
- (노드 개수 - 1)개의 간선을 선택하면 MST 완성이므로 더 이상 확인할 필요 없음.

<br>

### 🔷 크루스칼 알고리즘의 동작 과정

1️⃣ 간선을 비용 기준으로 오름차순 정렬

2️⃣ 가장 작은 비용의 간선부터 선택 (사이클이 발생하지 않도록 유니온 파인드 활용)

3️⃣ 총 (노드 개수 - 1)개의 간선을 선택하면 종료

<br>

<img src="https://gmlwjd9405.github.io/images/algorithm-mst/kruskal-example2.png">

```

static class Edge implements Comparable<Edge>{
    int from, to, cost;

    Edge(int from, int to, int cost){
        this.from = from;
        this.to = to;
        this.cost = cost;
    }

    @Override
    public int compareTo(Edge o){
        return this.cost - o.cost; // 비용 기준 오름차순 정렬
    }
}

// 루트 노드 찾기 (경로 압축)
static int find(int x){
    if(parent[x] != x){
        parent[x] = find(parent[x]);
    }

    return parent[x];
}

// 두 노드를 같은 집합으로 합치기 (랭크 기반)
static boolean union(int a, int b){
    int rootA = parent[a];
    int rootB = parent[b];

    if(rootA != rootB){
        // 랭크가 높은 트리에 낮은 트리를 합친다.
        if(rank[rootA] > rank[rootB]){
            parent[rootB] = rootA;
        } else if (rank[rootA] < rank[rootB]){
            parent[rootA] = rootB;
        } else { // 랭크가 같으면 하나를 루트로 만들고 랭크를 증가
            parent[rootB] = rootA;
            rank[rootA]++;
        }
        return true; // 연결 성공
    }
    return false; // 이미 같은 집합이면 연결하지 않음
}
```