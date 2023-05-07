//line share button box
const lineBtn=document.getElementById("line-button-box");
const thank=document.getElementById("line-thank-button")
lineBtn.addEventListener("click",()=>{
   thank.classList.remove("displayNone");
   thank.classList.add("line-thank-animation");
})



//about calculation
let divisionNumber=0;
const statistics1=document.getElementById("argmin-solo");
const statistics2=document.getElementById("argmin-solo-only-beta0");
const statistics3=document.getElementById("argmin-solo-only-beta1");
const statistics4=document.getElementById("mean");
const statistics5=document.getElementById("variance");
const statistics6=document.getElementById("covariance");
const statistics7=document.getElementById("population-mean");
const statistics8=document.getElementById("population-variance");
const statistics9=document.getElementById("uncertainty");
const statistics10=document.getElementById("x+uncertainty");

const statArr=["space",statistics1,statistics2,statistics3,statistics4,statistics5,statistics6,statistics7,statistics8,statistics9,statistics10];

for(let j=1;j<statArr.length;j++){
   statArr[j].addEventListener("click",()=>{
      
      divisionNumber=j;
   
      for(let i=1;i<statArr.length;i++){
         if(i != divisionNumber){
            statArr[i].style.color="black";
            statArr[i].style.backgroundColor="rgb(236, 236, 236)";
         }else{
            statArr[i].style.color="white";
            statArr[i].style.backgroundColor="#ae3ce3";
         }
      }
   
      if(j===1 || j===2 || j===3 || j===6){
         document.getElementById("input-text-second").classList.remove("displayNone");
      }else{
         document.getElementById("input-text-second").classList.add("displayNone");
      }

   })
}




function getArr1Func(input1){    //1st valuesの配列を生成＆全角入力へのアラート
   const inputTextArr1=input1.split(",");
   const inputArr1=[];
   for(let i=0;i<inputTextArr1.length;i++){
      if( inputTextArr1.indexOf("０") != -1 || inputTextArr1.indexOf("１") != -1 || inputTextArr1.indexOf("２") != -1 || inputTextArr1.indexOf("３") != -1 || inputTextArr1.indexOf("４") != -1 || inputTextArr1.indexOf("５") != -1 || inputTextArr1.indexOf("６") != -1 || inputTextArr1.indexOf("７") != -1 || inputTextArr1.indexOf("８") != -1 || inputTextArr1.indexOf("９") != -1 ){
         alert("半角で入力してください");
         break;
      }
      let inputArr1element=parseFloat(inputTextArr1[i]);
      inputArr1.push(inputArr1element);
   }
   return inputArr1;
}

function getArr2Func(input2){    //2nd valuesの配列を生成
   const inputTextArr2=input2.split(",");
   const inputArr2=[];
   for(let i=0;i<inputTextArr2.length;i++){
      let inputArr2element=parseFloat(inputTextArr2[i]);
      inputArr2.push(inputArr2element);
   }
   return inputArr2;
}


function meanFunc(Arr){    //平均値を求める
   let sum=0;
   for(let i=0;i<Arr.length;i++){
      sum+=Arr[i];
   }
   let mean=sum / Arr.length;
   return mean;
}

function squareMeanFunc(Arr){    //2乗の平均値を求める
   let squareSum=0;
   for (let i=0;i<Arr.length;i++){
      squareSum+=Arr[i] ** 2;
   }
   let squareMean=squareSum / Arr.length;
   return squareMean;
}

function productMeanFunc(Arr1,Arr2){    //積の平均値を求める
   let productSum=0;
   for(let i=0;i<Arr1.length;i++){
      productSum+=Arr1[i] * Arr2[i];
   }
   let productMean=productSum / Arr1.length;
   return productMean;
}



const inputButton=document.getElementById("input-button");

inputButton.addEventListener("click",()=>{
   let Arr1=getArr1Func(document.getElementById("input-text").value);
   const pointer=document.getElementById("memory-dammy");

   switch(divisionNumber){
      case 1:    //argmin-solo
         let Arr2In1=getArr2Func(document.getElementById("input-text-second").value);
         let meanX1=meanFunc(Arr1);
         let meanY1=meanFunc(Arr2In1);
         let varianceX1=squareMeanFunc(Arr1) - meanFunc(Arr1) ** 2;
         let covariance1=productMeanFunc(Arr1,Arr2In1) - meanFunc(Arr1)*meanFunc(Arr2In1);
         let beta_1In1=covariance1/varianceX1;
         let beta_0In1=meanY1 - beta_1In1 * meanX1;
         console.log(`(β0,β1) = (${beta_0In1}, ${beta_1In1})`);

         let item1=document.createElement("p");
         item1.textContent=`(β0,β1) = (${Math.round(beta_0In1*1000)/1000}, ${Math.round(beta_1In1*1000)/1000})`;
         pointer.prepend(item1);
         break;

      case 2:    //argmin-solo-only-beta0
         let Arr2In2=getArr2Func(document.getElementById("input-text-second").value);
         let beta_0In2=meanFunc(Arr2In2);
         console.log(beta_0In2);

         let item2=document.createElement("p");
         item2.textContent=`β0 = ${Math.round(beta_0In2*1000)/1000}`;
         pointer.prepend(item2);
         break;

      case 3:    //argmin-solo-only-beta1
         let Arr2In3=getArr2Func(document.getElementById("input-text-second").value);
         let beta_1In3=productMeanFunc(Arr1,Arr2In3) / squareMeanFunc(Arr1);
         console.log(beta_1In3);

         let item3=document.createElement("p");
         item3.textContent=`β1 = ${Math.round(beta_1In3*1000)/1000}`;
         pointer.prepend(item3);
         break;

      case 4:    //mean
         let mean4=meanFunc(Arr1);
         console.log(mean4);

         let item4=document.createElement("p");
         item4.textContent=`x- = ${Math.round(mean4*1000)/1000}`;
         pointer.prepend(item4);
         break;

      case 5:    //variance
         let variance5=squareMeanFunc(Arr1) - meanFunc(Arr1) ** 2;
         console.log(variance5);

         let item5=document.createElement("p");
         item5.textContent=`Sxx = ${Math.round(variance5*1000)/1000}`;
         pointer.prepend(item5);
         break;

      case 6:    //covariance
         let Arr2In6=getArr2Func(document.getElementById("input-text-second").value);
         let covariance6=productMeanFunc(Arr1,Arr2In6) - meanFunc(Arr1)*meanFunc(Arr2In6);
         console.log(covariance6);

         let item6=document.createElement("p");
         item6.textContent=`Sxy = ${Math.round(covariance6*1000)/1000}`;
         pointer.prepend(item6);
         break;

      case 7:    //population-mean
         let populationMean7=meanFunc(Arr1);
         console.log(populationMean7);

         let item7=document.createElement("p");
         item7.textContent=`μ = ${Math.round(populationMean7*1000)/1000}`;
         pointer.prepend(item7);
         break;
      
      case 8:    //population-variance
         let variance8=squareMeanFunc(Arr1) - meanFunc(Arr1) ** 2;
         let populationVariance8=(Arr1.length/(Arr1.length-1))*variance8;
         console.log(populationVariance8);

         let item8=document.createElement("p");
         item8.textContent=`σ^2 = ${Math.round(populationVariance8*1000)/1000}`;
         pointer.prepend(item8);
         break;

      case 9:    //uncertainty
         let variance9=squareMeanFunc(Arr1) - meanFunc(Arr1) ** 2;
         let populationVariance9=(Arr1.length/(Arr1.length-1))*variance9;
         let uncertainty9=populationVariance9 ** (1/2);
         console.log(uncertainty9);

         let item9=document.createElement("p");
         item9.textContent=`σ = ${Math.round(uncertainty9*1000)/1000}`;
         pointer.prepend(item9);
         break;

      case 10:    //x±uncertainty
         let variance10=squareMeanFunc(Arr1) - meanFunc(Arr1) ** 2;
         let populationVariance10=(Arr1.length/(Arr1.length-1))*variance10;
         let uncertainty10=populationVariance10 ** (1/2);
         let populationMean10=meanFunc(Arr1);
         let x_uncertainty10=populationMean10+" "+"±"+" "+uncertainty10;
         console.log(x_uncertainty10);

         let item10=document.createElement("p");
         item10.textContent=`x±Δx = ${Math.round(populationMean10*1000)/1000} ± ${Math.round(uncertainty10*1000)/1000}`;
         pointer.prepend(item10);
         break;


         

      default:
         console.log("Error");
   }
})

