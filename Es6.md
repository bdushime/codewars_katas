Who ate the cookie??

  function cookie(x){
  
  return typeof(x) === 'string'? 'Who ate the last cookie? It was Zach!' : typeof(x) === 'number' ? 'Who ate the last cookie? It was Monica!'
  : 'Who ate the last cookie? It was the dog!'
}

   
No Loops 1 - Small enough?

function smallEnough(a, limit){
    return a.every(num=> num <=limit)
}


Smallest value of an array

  function min(arr, toReturn) { 
   let minValue = Math.min(...arr);

  let minIndex = arr.indexOf(minValue);

  if (toReturn === "value") {
    return minValue;
  } else if (toReturn === "index") {
    return minIndex;
  } else {
    return null; 
  }
}




Homogenous arrays

  function filterHomogenous(arrays) {
  return arrays.filter(subArr => {
    if (subArr.length === 0) return false; 
    
    let firstType = typeof subArr[0];
    
    return subArr.every(item => typeof item === firstType);
  });
}














Find Maximum and Minimum Values of a List

  var min = function(list) {
  let smallest = list[0];
  for (let i = 1; i < list.length; i++) {
    if (list[i] < smallest) {
      smallest = list[i];
    }
  }
  return smallest;
}

var max = function(list) {
  let largest = list[0];
  for (let i = 1; i < list.length; i++) {
    if (list[i] > largest) {
      largest = list[i];
    }
  }
  return largest;
}









Is a number prime?

   function isPrime(num) {
  if (num <= 1) return false;       
  if (num === 2) return true;       
  if (num % 2 === 0) return false;  

  const limit = Math.sqrt(num);
  for (let i = 3; i <= limit; i += 2) {
    if (num % i === 0) return false;
  }

  return true;
}










List Filtering

 function filter_list(l) {
  
  return l.filter(item=> typeof item === 'number')
  
}





How many socks for a pair?

  function socks(colours,pairs) {
   if (pairs === 0) return 0;
    return 2 * pairs + (colours - 1);
}








Did someone say cake?

   function cake(ingredient, amount) {
  const recipe = {
    'caster sugar': { amount: 160, unit: 'g' },
    butter: { amount: 170, unit: 'g' },
    eggs: { amount: 3, unit: '' }, 
    'self-raising flour': { amount: 115, unit: 'g' },
    'cocoa powder': { amount: 55, unit: 'g' }
  };

  const factor = amount / recipe[ingredient].amount;

  const adjusted = {};
  for (let key in recipe) {
    let newAmount = recipe[key].amount * factor;
    
    newAmount = Math.round(newAmount * 10) / 10;
    adjusted[key] = recipe[key].unit ? `${newAmount}${recipe[key].unit}` : newAmount;
  }

  return adjusted;
}













export const digitalRoot = (n:number):number => {

 while (n >= 10) {
        n = n.toString()
            .split('')
            .reduce((sum: number, digit: string) => sum + parseInt(digit), 0);
    }
    return n;

}

Not very secure

   function alphanumeric(string) {
  if (string.length === 0) return false;

  for (let i = 0; i < string.length; i++) {
    const c = string[i];
    let upper = false;
    let lower = false;
    let digit = false;

    const code = c.charCodeAt(0);

    if (code >= 65 && code <= 90) {
      upper = true;
    } else if (code >= 97 && code <= 122) {
      lower = true;
    } else if (code >= 48 && code <= 57) {
      digit = true;
    }

    if (!upper && !lower && !digit) {
      return false;
    }
  }
  return true;
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



function isPangram(string) {
    let strT = string.toLowerCase().replace(/[^a-z]/g, ''); // Convert to lowercase and remove non-alphabetic characters
    let uniqueLetters = new Set(); // Set to store unique letters

    for(let i=0;i<strT.length;i++){
      let char=strT[i];
      
      if(char>='a'&& char<='z'){
        uniqueLetters.add(char);
      }
      
       if(uniqueLetters.size === 26){
    return true;
  }
      
    }
 
  
    return false;
  
}
      
