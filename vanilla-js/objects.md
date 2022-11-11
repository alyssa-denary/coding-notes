## Using the spread operator with Objects
//declare function takes obj, add prop, returns obj

const testObject = {};

const newObj = addColor(testObject); // {color: "orange"}

  

function addColor(obj){

const newObj = {...obj};

newObj['color'] = "orange";

return newObj;

}
