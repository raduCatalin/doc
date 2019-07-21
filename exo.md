// Bubble Sort

let sequence = [5, 9, 3, 1, 2, 8, 4, 7, 6];

const len = sequence.length;

for(let sortEdge=0; sortEdge<=len-2; sortEdge++){

	for(let i=len-1; i>=sortEdge; i--){
		//if i=0 then don't do i-1
		if(i && sequence[i] < sequence[i-1]){ 
			const temp = sequence[i];
			sequence[i] = sequence[i-1];
			sequence[i-1] = temp;
		}	
	}
}
console.log(sequence);
