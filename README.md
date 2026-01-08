// 1. Create a Promise
const myPromise = new Promise((resolve, reject loop,result logic positive) => {
  //  Asynchronous operation ( random number,array)
  setTimeout((1000) => {
    const success = false; // Set to false to see the reject path
    if (success) {
      resolve(" change sign another, number another"); // Promise fulfilled
    } else {
      reject("Start over"); // Promise rejected
    }
  }, 10000); // Waits 10 second
});

// 2. Consume the Promise
myPromise
  .then((result) => { // Runs if resolve() is called
    console.log("Success:", result);
    return "Processed data"; // Return value for the next .then()
  })
  .then((processedResult) => {
    console.log("Next step:", processedResult);
  })
  .catch((error) => { // Runs if reject() is called
    console.error("Error:", error);
  })
  .finally(() => { // Runs regardless of success or failure
    console.log("Promise settled (finished).");
  });

// Using Promise.all() for multiple promises
const promise1 = Promise.resolve("First task done");
const promise2 = new Promise((resolve, reject) => setTimeout(resolve, 500, 'Second task done'));

Promise.all([promise1, promise2])
  .then((results) => {
    console.log("All tasks done:", results); // [ 'First task done', 'Second task done' ]
  })
  .catch(err => console.error(err));

