{/* === Passo 1: Nome do item (colocar dentro do container h-72) === */}
<div className="space-y-4">
  {cart.map((item, index) => (
    <div key={`${item.id}-${index}`} className="pb-2 border-b border-gray-200">
      {/* Parte 1: Nome do produto */}
      <div className="flex justify-between items-center">
        <p className="font-semibold text-lg">{item.name}</p>
        <button
          onClick={() => removeFromCart(item.id)}
          className="text-red-600 hover:text-red-800"
          aria-label={`Remover ${item.name}`}
        >
          <RiSubtractFill />
        </button>
      </div>
      {/* OBS: por enquanto não renderizamos preço/quantidade; só o nome */}
    </div>
  ))}
</div>
