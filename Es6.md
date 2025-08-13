
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

      
