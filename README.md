# merge-sort-solution

function merge(array) {
  if (array.length < 2) return array;
  const mid = Math.floor(array.length / 2);
  const leftArr = array.slice(0, mid);
  const rightArr = array.slice(mid);
  return sort(merge(leftArr), merge(rightArr));
}

function sort(leftArr, rightArr) {
  let temporaryArr = [];
  while (leftArr.length + rightArr.length > 0) {
    if (leftArr.length < 1) {
      temporaryArr.push(...rightArr.splice(0, 1));
    }
    if (rightArr.length < 1) {
      temporaryArr.push(...leftArr.splice(0, 1));
    }
    if (leftArr[0] < rightArr[0]) {
      temporaryArr.push(...leftArr.splice(0, 1));
    } else temporaryArr.push(...rightArr.splice(0, 1));
  }
