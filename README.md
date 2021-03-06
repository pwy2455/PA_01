# PA_01
## File list
readme PA_01.cpp inputf1.txt inputf2.txt outputf1.txt outputf2.txt
## Command Line Arguments
## Description of your code
배열을 정렬해주는 Sotring, 배열의 원소를 더하고 뺴는 remove, insert, n!의 값을 주는 factorial, 정렬된 순열을 원소로 갖는 배열 C에서 각 원소의 위치를 잡아주는 findK, 입력된 배열을 순열로 만들어주는 permutating 함수로 구성됩니다. 
외부의 파일을 받아 행렬 text에 저장합니다. 이후 text의 크기를 size라 하여 A에는 1~size까지의 숫자를 할당하고 B는 size x size만큼의 배열로 정의하고 C는 size! x size만큼의 배열로 정의합니다. 배열 A, B, C와 정수 size를함수 permutating에 넣습니다. 배열 A의 원소를 위치 순서대로 하나씩 배열 B에 넣습니다. 이때 함수는 재귀함수로 함수가 시작되면 정수 d가 1 증가하고, 함수를 빠져나올 때 1 감소합니다. 배열 B에는 d값에 따라 A로 부터 받는 값이 누적되어 저장됩니다. 각각의 d에 대해서 for문을 돌려 각각의 for문의 모든 경우를 만들 수 있도록 합니다.
ex) 첫번째 순열을 만들 때
d=0 A=[1,2,3,4,5] B=[]
d=1 A=[2,3,4,5]   B=[[1][1][1][1]]
d=2 A=[3,4,5]     B=[[1][1,2][1,2][1,2]]
d=3 A=[4,5]       B=[[1][1,2][1,2,3][1,2,3]]
d=4 A=[5]         B=[[1][1,2][1,2,3][1,2,3,4]]
만약 A의 크기가 1이 되면 B[3]과 A를 합친 배열[1,2,3,4,5]을 C(k=0)에 넣어줍니다. 이후 마지막 재귀함수에서 탈출해 d=3으로 돌아갑니다. 이후 함수를 반복합니다.
ex) 두번째 순열을 만들 때
d=3 A=[4,5]       B=[[1][1,2][1,2,3][1,2,3]]
d=4 A=[4]         B=[[1][1,2][1,2,3][1,2,3,5]]
B의 4를 다시 A로 넣어준 뒤 A의 다음 숫자인 5를 B에 넣습니다. 이런 방식으로 C에 n!개의 배열이 들어올 때 까지 반복합니다.
C의 배열이 n!개가 되면 순열화된 각 숫자들을 원래 sorting된 배열 sorted_text에 대응하여 원래 문자로 출력합니다.
본 방식으로는 중복되는 순열을 뺄 수 없는 한계가 있습니다.
## Algorithmic Analysis
실제 순열의 조합 과정을 재현했으므로 O(n)=nPn=n!입니다.
