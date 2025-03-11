Find twins:

1st way:
       function elimination(arr){
  const uniqueSet = new Set();
  for(let key of arr){
    if(uniqueSet.has(key)){
      return Number(key);
    }
    uniqueSet.add(key);
  }
  return null;
}


2nd way:

      
