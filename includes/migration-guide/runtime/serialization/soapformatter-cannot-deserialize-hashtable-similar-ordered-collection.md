### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="6ca9d-101">SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares</span><span class="sxs-lookup"><span data-stu-id="6ca9d-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6ca9d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6ca9d-102">Details</span></span>|<span data-ttu-id="6ca9d-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión.</span><span class="sxs-lookup"><span data-stu-id="6ca9d-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="6ca9d-104">En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=name>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET 4.0 si se serializaron con .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="6ca9d-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=name>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET 4.0 if they were serialized with .NET 4.5.</span></span> <span data-ttu-id="6ca9d-105">Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.</span><span class="sxs-lookup"><span data-stu-id="6ca9d-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>|
|<span data-ttu-id="6ca9d-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6ca9d-106">Suggestion</span></span>|<span data-ttu-id="6ca9d-107">La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> para que sea resistente a los cambios de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ca9d-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> to be resilient to .NET Framework changes.</span></span>|
|<span data-ttu-id="6ca9d-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6ca9d-108">Scope</span></span>|<span data-ttu-id="6ca9d-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6ca9d-109">Minor</span></span>|
|<span data-ttu-id="6ca9d-110">Versión</span><span class="sxs-lookup"><span data-stu-id="6ca9d-110">Version</span></span>|<span data-ttu-id="6ca9d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="6ca9d-111">4.5</span></span>|
|<span data-ttu-id="6ca9d-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ca9d-112">Type</span></span>|<span data-ttu-id="6ca9d-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6ca9d-113">Runtime</span></span>|
|<span data-ttu-id="6ca9d-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6ca9d-114">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
