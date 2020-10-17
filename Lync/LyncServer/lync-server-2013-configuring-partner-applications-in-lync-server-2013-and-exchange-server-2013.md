---
title: Configuration des applications partenaires dans Lync Server 2013 et Exchange Server 2013
description: Configuration des applications partenaires dans Lync Server 2013 et Exchange Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b149642e7b81a3e8befd321c3a62c8ceeeb00eac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548320"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="f55cc-103">Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55cc-103">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55cc-104">_**Dernière modification de la rubrique :** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="f55cc-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="f55cc-p101">L’authentification de serveur à serveur implique généralement trois entités : les deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si deux serveurs (par exemple Serveur A et Serveur B) doivent communiquer, tous deux commencent en général par contacter un serveur d’émission de jetons et afin d’obtenir un jeton de sécurité approuvé mutuellement. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.</span><span class="sxs-lookup"><span data-stu-id="f55cc-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="f55cc-108">Ceci n’est toutefois qu’une règle générale.</span><span class="sxs-lookup"><span data-stu-id="f55cc-108">However, that's a general rule.</span></span> <span data-ttu-id="f55cc-109">Lync Server 2013, Microsoft Exchange Server 2013 et Microsoft SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur de jetons tiers lors de la communication les uns avec les autres ; Cela est dû au fait que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés les uns avec les autres sans avoir besoin d’un serveur de jetons distinct.</span><span class="sxs-lookup"><span data-stu-id="f55cc-109">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="f55cc-110">(Cette fonctionnalité est disponible uniquement dans Lync Server 2013, Exchange 2013 et SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cc-110">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="f55cc-111">Si vous devez configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveurs Microsoft, vous devrez faire appel à un serveur d’émission de jetons tiers.)</span><span class="sxs-lookup"><span data-stu-id="f55cc-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="f55cc-112">Pour configurer l’authentification de serveur à serveur entre Lync Server et Exchange, vous devez effectuer deux opérations : 1) vous devez affecter les certificats appropriés à chaque serveur ; et, 2) vous devez configurer chaque serveur de sorte qu’il soit une application partenaire de l’autre serveur : cela signifie que vous devez configurer Lync Server 2013 comme application partenaire pour Exchange 2013 et vous devez configurer Exchange 2013 comme application partenaire pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cc-112">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="f55cc-113">Configuration de Lync Server 2013 comme application partenaire pour Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="f55cc-113">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="f55cc-114">Le moyen le plus simple de configurer Lync Server 2013 comme application partenaire avec Exchange 2013 est d’exécuter le script Configure-EnterprisePartnerApplication.ps1, un script Windows PowerShell fourni avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cc-114">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="f55cc-115">Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées d’authentification Lync Server ; Il s’agit généralement du nom de domaine complet du pool Lync Server 2013 suivi du suffixe/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="f55cc-115">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f55cc-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f55cc-116">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="f55cc-117">Pour configurer Lync Server en tant qu’application partenaire, ouvrez l’environnement de commande Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant qu’Exchange a été installé sur le lecteur C : et qu’il utilise le chemin d’accès au dossier par défaut) :</span><span class="sxs-lookup"><span data-stu-id="f55cc-117">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="f55cc-118">Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer les services Internet (IIS) sur vos serveurs de boîtes aux lettres et d’accès au client Exchange.</span><span class="sxs-lookup"><span data-stu-id="f55cc-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="f55cc-119">Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :</span><span class="sxs-lookup"><span data-stu-id="f55cc-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="f55cc-120">Cette commande peut être exécutée à partir de l’environnement de commande Exchange Management Shell ou de toute autre fenêtre de commande exécutée sous les privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f55cc-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="f55cc-121">Configuration d’Exchange 2013 comme application partenaire pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55cc-121">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="f55cc-122">Une fois que vous avez configuré Lync Server 2013 comme application partenaire pour Exchange 2013, vous devez configurer Exchange comme application partenaire pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f55cc-122">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="f55cc-123">Ceci peut être réalisé à l’aide de Lync Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange ; Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi du suffixe/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="f55cc-123">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f55cc-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f55cc-124">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="f55cc-125">Dans Lync Server, les applications partenaires sont configurées à l’aide de la cmdlet [New-applet cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="f55cc-125">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="f55cc-126">En plus de spécifier l’URI de métadonnées, vous devez également définir le niveau de confiance Full pour l’application ; Cela permet à Exchange de se représenter lui-même et tout utilisateur autorisé dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="f55cc-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="f55cc-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f55cc-127">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="f55cc-128">Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script figurant dans la documentation de l’authentification de serveur à serveur de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cc-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="f55cc-129">Pour plus d’informations, reportez-vous à l’article [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="f55cc-129">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="f55cc-130">Si vous avez réussi à configurer les applications partenaires pour Lync Server et Exchange, cela signifie que vous avez également réussi à configurer l’authentification de serveur à serveur entre les deux produits.</span><span class="sxs-lookup"><span data-stu-id="f55cc-130">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="f55cc-131">Lync Server 2013 inclut une applet de commande Windows PowerShell, [test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), qui vous permet de vérifier que l’authentification de serveur à serveur a été correctement configurée et que le service de stockage Lync Server peut se connecter à Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cc-131">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="f55cc-132">L’applet de commande effectue cette opération en se connectant à la boîte aux lettres d’un utilisateur Exchange 2013, en écrivant un élément dans le dossier historique des conversations de cet utilisateur, puis en supprimant éventuellement cet élément.</span><span class="sxs-lookup"><span data-stu-id="f55cc-132">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="f55cc-133">Pour tester l’intégration de Lync Server 2013 et Exchange 2013, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f55cc-133">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="f55cc-134">Dans la commande précédente, SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur Exchange 2013. votre commande échouera dans ce n’est pas un compte d’utilisateur valide.</span><span class="sxs-lookup"><span data-stu-id="f55cc-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="f55cc-135">Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="f55cc-135">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

