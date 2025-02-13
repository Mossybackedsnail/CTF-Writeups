## Javascryption -- aplet123

You wake up alone in a dark cabin, held captive by a bushy-haired man demanding you submit a "flag" to leave. Can you escape?

## Solution

The website, resembling the cabin from "Inscryption", allows the user to input a flag and check to see if it is correct or not.

A quick look at the source shows the function responsible for checking:

```js
function checkFlag(flag) {
	const step1 = btoa(flag);
	const step2 = step1.split("").reverse().join("");
	const step3 = step2.replaceAll("Z", "[OLD_DATA]");
	const step4 = encodeURIComponent(step3);
	const step5 = btoa(step4);
	return step5 === "JTNEJTNEUWZsSlglNUJPTERfREFUQSU1RG85MWNzeFdZMzlWZXNwbmVwSjMlNUJPTERfREFUQSU1RGY5bWI3JTVCT0xEX0RBVEElNURHZGpGR2I=";
	}
```

Evidently the base64 string at the end is our flag and so a quick reversal of the steps should lead to the solution.

1. Runing the string through a base64 decryptor gets us:
    ```%3D%3DQflJX%5BOLD_DATA%5Do91csxWY39VespnepJ3%5BOLD_DATA%5Df9mb7%5BOLD_DATA%5DGdjFGb```
    
1. encodeURIComponent just replaces specific characters with an escape sequence, i.e. ] -> %5D, # - > %23, etc. There are plenty of online tools that allow you to reverse URL encoded strings so running the code through one of those yields:
```==QflJX[OLD_DATA]o91csxWY39VespnepJ3[OLD_DATA]f9mb7[OLD_DATA]GdjFGb```

1. Then, all of the instances of  ```[OLD_DATA]``` should be replaced with ```Z``` in accordance with step 3.
```==QflJXZo91csxWY39VespnepJ3Zf9mb7ZGdjFGb```

1. Lastly, simply reverse the string and run it through a base64 decoder once more to reveal the flag:  
```
lactf{no_grizzly_walls_here}
```
---