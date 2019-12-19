# React things

Ejemplo basico hooks:
´´´
const component = (props) =>{
	const [count, setCount] = useState(1);
	
	const incrementarContador = function(){
		setCount(count+1);
	};
	
	return (<>
		<span>{count}</span>
		<a onClick={incrementarContador}>Incrementar</a>
	</>);
};
´´´