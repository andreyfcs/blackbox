import { useEffect, useRef } from "react";

const PDVView = () => {
  const scrollRef = useRef(null);

  useEffect(() => {
    if (scrollRef.current) {
      // Rola até o final da div sempre que o carrinho for atualizado
      scrollRef.current.scrollTop = scrollRef.current.scrollHeight;
    }
  }, [cart]); // dispara sempre que o carrinho muda

  return (
    <div
      ref={scrollRef}
      className="
        bg-white border-2 rounded p-4 
        w-full sm:w-[90%] md:w-[70%] lg:w-[35%] 
        h-auto max-h-[80vh] overflow-y-auto 
        mx-auto mt-4
      "
    >
      {cart.length > 0 ? (
        <div className="overflow-x-auto">
          <table className="w-full text-center border-collapse">
            <thead>
              <tr className="bg-gray-100">
                <th className="py-2">Item</th>
                <th className="py-2">Qtd</th>
                <th className="py-2">Preço Unitário</th>
                <th className="py-2">Remover</th>
              </tr>
            </thead>
            <tbody>
              {cart.map((item, index) => (
                <tr key={`${item.id}-${index}`} className="border-b">
                  <td>{item.name}</td>
                  <td>{item.quantity}</td>
                  <td>R${Number(item.price).toFixed(2)}</td>
                  <td>
                    <button
                      onClick={() => removeFromCart(item.id)}
                      className="text-red-600 hover:text-red-800"
                    >
                      <RiSubtractFill />
                    </button>
                  </td>
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      ) : (
        <p className="text-center text-gray-500">O carrinho está vazio.</p>
      )}
    </div>
  );
};
