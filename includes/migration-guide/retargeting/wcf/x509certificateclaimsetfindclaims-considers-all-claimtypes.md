### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="cf4ee-101">X509CertificateClaimSet.FindClaims considera todos los argumentos claimType</span><span class="sxs-lookup"><span data-stu-id="cf4ee-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cf4ee-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="cf4ee-102">Details</span></span>|<span data-ttu-id="cf4ee-103">En las aplicaciones destinadas a .NET Framework 4.6.1, si un conjunto de notificaciones X509 se inicializó desde un certificado con varias entradas DNS en su campo SAN, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> trata de hacer coincidir el argumento claimType con todas las entradas DNS. En las aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> solo trata de hacer coincidir el argumento claimType con la última entrada DNS.</span><span class="sxs-lookup"><span data-stu-id="cf4ee-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> method attempts to match the claimType argument only with the last DNS entry.</span></span>|
|<span data-ttu-id="cf4ee-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="cf4ee-104">Suggestion</span></span>|<span data-ttu-id="cf4ee-105">Este cambio solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="cf4ee-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="cf4ee-106">Este cambio puede deshabilitarse (o habilitarse si se establece como destino una versión anterior a la 4.6.1) con el modificador de compatibilidad [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).</span><span class="sxs-lookup"><span data-stu-id="cf4ee-106">This change may be disabled (or enabled if targetting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>|
|<span data-ttu-id="cf4ee-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="cf4ee-107">Scope</span></span>|<span data-ttu-id="cf4ee-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="cf4ee-108">Minor</span></span>|
|<span data-ttu-id="cf4ee-109">Versión</span><span class="sxs-lookup"><span data-stu-id="cf4ee-109">Version</span></span>|<span data-ttu-id="cf4ee-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="cf4ee-110">4.6.1</span></span>|
|<span data-ttu-id="cf4ee-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="cf4ee-111">Type</span></span>|<span data-ttu-id="cf4ee-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="cf4ee-112">Retargeting</span></span>|
|<span data-ttu-id="cf4ee-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cf4ee-113">Affected APIs</span></span>|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|
