export const digitallRoot = (n:number):number => {

 while (n >= 10) {
        n = n.toString()
            .split('')
            .reduce((sum: number, digit: string) => sum + parseInt(digit), 0);
    }
    return n;

}











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
  return null;;
}


2nd way:

function elimination(arr){
  //write your code here 
  let obj={};
  
  for(let item of arr){
    obj[item]=(obj[item] || 0) + 1;
  }
  
  let max=null;
  for(let key in obj){
      if(obj[key] > 1){
        max=Number(key);
      }
  
     
  }
  
  return max;
}

      
