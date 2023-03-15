비선형 자료 구조
=
- 비선형 자료 구조란 일렬로 나열하지 않고 자료의 순서나 관계가 복잡한 구조를 말합니다.
- 그래프
  - 그래프는 정점과 간선으로 이루어져 있는 자료 구조입니다.
  - 정점 : 어디서 어디를 간다라고 했을 때 어디 혹은 어떠한 곳을 정점(vertex)이라고 합니다.
  - 간선 : 어디서 어디를 갈 때 무엇을 통해 가는 그 무엇을 간선(edge)이라고 합니다.
    - 한 쪽으로만 갈 수 있는 간선을 단방향 간선, 양쪽 다 이동 가능한 간선을 양방향 간선이라고 합니다.
    - 현재 정점에서 나가는 간선을 outdegree, 들어오는 간선을 indegree라고 합니다.
  - 가중치 : 가중치는 간선과 정점 사이에 드는 비용을 뜻합니다.
---
- 트리
  - 트리는 그래프 중 하나로 그래프의 특징처럼 정점과 간선으로 이루어져 있습니다.
  - 트리 구조로 된 계층적 데이터의 집합입니다.
  - 루트 노드, 내부 노드, 리프 노드 등으로 이루어져 있습니다.
  - 루트 노드
  - 가장 위에 있는 노드를 뜻합니다.
  - 내부 노드
      - 루트 노드와 리프 노드 사이의 노드를 뜻합니다.
  - 리프 노드
      - 리프 노드는 자식이 없는 노드를 뜻합니다.
  - 트리의 특징
    - 트리는 그래프의 일종이지만 다음 특징을 가집니다.
    1. 부모, 자식 계층 구조를 가집니다.
    2. 간선 수 = 노드 수 - 1의 특징을 가집니다.
    3. 임의의 두 노드 사이의 경로는 '유일무이'하게 존재합니다. 트리 내의 어떤 노드와 어떤 노드까지 경로는 반드시 있습니다.
  - 이진 트리
    - 이진 트리는 자식의 수가 두 개 이하인 트리를 말합니다.
    - 이진 트리의 종류
      - 정이진 트리(full binary tree) : 자식 노드의 수가 0 또는 두 개인 이진 트리를 말합니다.
      - 완전 이진 트리(complete binary tree) : 왼쪽에서부터 채워져 있는 이진 트리를 말합니다.
      - 변질 이진 트리(degenerate binary tree) : 자식 노드가 하나밖에 없는 이진 트리를 말합니다.
      - 포화 이진 트리(perfect binary tree) : 모든 노드가 꽉 차있는 이진 트리를 말합니다.
      - 균형 이진 트리(balanced binary tree) : 왼쪽과 오른쪽 노드의 높이 차이가 1 이하인 이진 트리를 말합니다.
    - 이진 탐색 트리(BST, Binary Search Tree)
      - 이진 탐색 트리는 노드의 오른쪽 하위 트리에는 '큰 값'이 왼쪽 하위 트리에는 '작은 값'이 있는 트리를 말합니다.
      - 평균적으로 이진 탐색 트리는 O(logn)의 시간이 걸리지만 한 쪽으로 편향된 최악의 트리의 경우 O(n)이 걸리게 됩니다. ex) 5 - 4 - 3 - 2 - 1
    - AVL 트리(Adelson-Velsky and Landis tree)
      - 이진 탐색 트리의 최악의 경우 O(n)의 시간 복잡도를 갖는 문제를 방지하고 스스로 균형을 잡는 이진 탐색 트리입니다.
      - 두 자식의 서브 트리의 높이 차이가 최대 1만큼 차이 난다는 특징이 있습니다.
      - 균형을 잡기 위해 트리의 일부를 왼쪽, 오른쪽으로 회전 시키며 균형을 잡습니다.
    - 레드 블랙 트리
      - 레드 블랙 트리는 균형 이진 탐색 트리로 탐색, 삽입, 삭제 모두 시간 복잡도가 O(logn)입니다.
      - 각 노드는 빨간색 또는 검은색의 색상을 나타내는 추가 비트를 저장합니다.
      - 삽입 및 삭제 중에 트리가 균형을 유지하도록 하는데 사용됩니다.
      - "모든 리프 노드와 루트 노드는 블랙이고 어떤 노드가 레드이면 그 노드의 자식은 반드시 블랙이다."라는 규칙을 기반으로 균형을 잡는 트리입니다.
---
- 힙
  - 힙은 완전 이진 트리 기반의 자료 구조입니다.
  - 최소힙과 최대힙 두 가지가 있고 해당 힙에 따라 특정한 특징을 지킨 트리를 말합니다.
  - 최대힙 : 루트 노드에 있는 키는 모든 자식에 있는 키 중 가장 큰 값을 가집니다. 또한 각 노드의 자식 노드와의 관계도 이와 같은 특징을 가져야합니다.
  - 최소힙 : 최대힙의 반대로 루트 노드는 있는 키 중에 가장 작은 값을 가집니다. 마찬가지로 각 노드의 자식 노드와의 관계도 이와 같은 특징을 가져야합니다.
  - 삽입 과정
    - 새로운 데이터가 들어오면 우선 제일 마지막 노드로 추가합니다.
    - 새로운 노드를 부모 노드와 값을 비교하면서 힙의 성질을 만족 시킵니다.
  - 삭제 과정
    - 루트 노드를 삭제하고 가장 마지막 노드를 루트 노드로 스왑합니다.
    - 이후 자식 노드와 스왑을 하며 힙의 성질을 만족합니다.
---
- 우선순위 큐
  - 우선순위 큐는 우선순위 대기열이라고도 하며, 대기열에서 우선순위가 높은 요소를 우선순위가 낮은 요소보다 먼저 제공하는 자료 구조입니다.
  - 우선순위 큐는 힙을 기반으로 구현됩니다.
---
- 맵
  - 맵(map)은 특정 순서에 따라 키와 매핑된 값의 조합으로 형성된 자료 구조입니다.
  - 레드 블랙 트리를 기반으로 형성 되고 삽입하면 자동 정렬 됩니다.
  - map은 해시 테이블을 구현할 때 쓰며 정렬을 보장하지 않는 map과 보장하는 map 두 가지가 있습니다.
---
- 셋
  - 셋(set)은 특정 순서에 따라 고유한 요소를 저장하는 컨테이너이며, 중복되는 요소가 없고 오로지 유니크한 값만 저장하는 자료 구조입니다.
---
- 해시 테이블
  - 해시 테이블은 무한에 가까운 데이터들을 유한한 개수의 해시 값으로 매핑한 테이블입니다.
  - 삽입, 삭제, 탐색 시 평균적으로 O(1)의 시간 복잡도를 가집니다.