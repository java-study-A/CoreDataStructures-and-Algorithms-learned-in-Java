# 2-1-Selection-Sort
- 배열에서 가장 작은 요소를 찾아 배열의 맨 앞 요소와 교환
- 다음 작은 요소를 찾아 두번째 요소와 교환
- 이러한과정을 반복하여 배열 전체를 정렬
- 시간 복잡도는 항상 O(n^2)로 비효율적이라서 작은 데이터셋에만 적합
```Java
public class SelectionSort {

	/**
	 * Swaps the elements at indexes i and j.
	 */
	public static void swapElements(int[] array, int i, int j) {
		System.out.println("Swapping: " + i + " and " + j);
		int temp = array[i];
		array[i] = array[j];
		array[j] = temp;
	}

	/**
	 * Finds the index of the lowest value
	 * between indices low and high (inclusive).
	 */
	public static int indexLowest(int[] array, int start) {
		int lowIndex = start;
		for (int i = start; i < array.length; i++) {
			if (array[i] < array[lowIndex]) {
				lowIndex = i;
			}
		}
		return lowIndex;
	}

	/**
	 * Sorts the cards (in place) using selection sort.
	 */
	public static void selectionSort(int[] array) {
		for (int i = 0; i < array.length; i++) {
			int j = indexLowest(array, i);
			swapElements(array, i, j);
		}
	}

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		int[] array = {2, 5, 6, 1, 3};
		selectionSort(array);
		System.out.println(Arrays.toString(array));
	}

}
```
- swapElements: 배열의 두 요소를 교환하는 메서드 -> 요소를 읽고 쓰는 것은 상수시간 연산 
- indexLowest: 배열에서 가장 작은 요소의 인덱스를 찾는 메서드 -> 배열의 길이에 비례하는 시간이 걸림
  - 선형 시간 작업이므로 O(n)
- selectionSort: 배열을 정렬하는 메서드 -> indexLowest 메서드를 호출하고 swapElements 메서드를 호출
  - indexLowest 메서드를 호출하는 횟수는 배열의 길이에 비례
  - swapElements 메서드를 호출하는 횟수도 배열의 길이에 비례
  - 따라서 selectionSort 메서드의 시간 복잡도는 이차시간 O(n^2)