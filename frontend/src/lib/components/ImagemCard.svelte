<script>
    export let imageSrc; 
    export let name;     
</script>

<div class="card">
    <img src={imageSrc} alt={name} />  
    <p>{name}</p>                      
</div>

<style>
    .card {
        display: flex;
        flex-direction: column; 
        align-items: center;   
        border: 1px solid #ddd; 
        border-radius: 8px;    
        padding: 10px;          
        width: 150px;           
        margin: 10px;         
    }

    img {
        width: 100px;          
        height: 100px;         
        object-fit: cover;     
        border-radius: 50%;    
    }

    p {
        text-align: center;    
        margin-top: 8px;       
        font-weight: bold;   
    }
    
</style>
