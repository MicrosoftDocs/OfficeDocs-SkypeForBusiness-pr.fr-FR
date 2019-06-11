---
title: Configuration des applications partenaires dans Lync Server 2013 et Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="e2b7a-102">Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b7a-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b7a-103">_**Dernière modification de la rubrique:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e2b7a-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e2b7a-104">L’authentification de serveur à serveur implique généralement trois entités: les deux serveurs qui doivent communiquer entre eux et un serveur d’jetons de sécurité tiers.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="e2b7a-105">Si deux serveurs (par exemple, serveur A et serveur B) doivent communiquer, chacun de ces serveurs doit généralement commencer par contacter un serveur jeton et obtenir un jeton de sécurité digne de confiance.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="e2b7a-106">Le serveur A doit alors présenter ce jeton de sécurité au serveur B (et inversement) pour garantir son authenticité et sa fiabilité.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="e2b7a-107">Néanmoins, il s’agit d’une règle générale.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-107">However, that's a general rule.</span></span> <span data-ttu-id="e2b7a-108">Lync Server 2013, Microsoft Exchange Server 2013 et Microsoft SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur jeton tiers lors de la communication entre eux. ce n’est pas parce que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés l’un de l’autre sans qu’il soit nécessaire de recourir à un serveur jeton distinct.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="e2b7a-109">(Cette fonctionnalité est disponible uniquement dans Lync Server 2013, Exchange 2013 et SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="e2b7a-110">Si vous avez besoin de configurer l’authentification serveur à serveur avec d’autres serveurs, y compris d’autres produits Microsoft Server, vous devez le faire à l’aide d’un serveur de jetons tiers.)</span><span class="sxs-lookup"><span data-stu-id="e2b7a-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="e2b7a-111">Pour configurer l’authentification de serveur à serveur entre Lync Server et Exchange, vous devez effectuer deux opérations: 1) vous devez attribuer les certificats appropriés à chaque serveur. et 2) vous devez configurer chaque serveur pour qu’il soit une application partenaire de l’autre serveur: autrement dit, vous devez configurer Lync Server 2013 de manière à ce qu’il s’agit d’une application partenaire pour Exchange 2013 et vous devez configurer Exchange 2013 pour être une application partenaire pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="e2b7a-112">Configuration de Lync Server 2013 en tant qu’application partenaire pour Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="e2b7a-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="e2b7a-113">Le moyen le plus simple de configurer Lync Server 2013 comme application partenaire avec Exchange 2013 consiste à exécuter le script Configure-EnterprisePartnerApplication. ps1, un script Windows PowerShell fourni avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="e2b7a-114">Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées d’authentification de Lync Server. Il s’agit généralement du nom de domaine complet du pool Lync Server 2013 suivi du suffixe/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e2b7a-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2b7a-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="e2b7a-116">Pour configurer Lync Server en tant qu’application partenaire, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en partant du principe que Exchange a été installé sur le lecteur C, et qu’il utilise le chemin de dossier par défaut):</span><span class="sxs-lookup"><span data-stu-id="e2b7a-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="e2b7a-117">Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur votre boîte aux lettres Exchange et les serveurs d’accès au client.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="e2b7a-118">Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :</span><span class="sxs-lookup"><span data-stu-id="e2b7a-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="e2b7a-119">Vous pouvez exécuter cette commande à partir de Exchange Management Shell ou de n’importe quelle autre fenêtre de commande sous privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="e2b7a-120">Configuration d’Exchange 2013 pour être une application partenaire pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b7a-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="e2b7a-121">Une fois que vous avez configuré Lync Server 2013 comme application partenaire pour Exchange 2013, vous devez ensuite configurer Exchange en tant qu’application partenaire de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="e2b7a-122">Vous pouvez effectuer cette opération à l’aide de Lync Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange. Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi du suffixe/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e2b7a-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2b7a-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="e2b7a-124">Dans Lync Server, les applications partenaires sont configurées à l’aide de l’applet [de nouvelle applet de nouveau-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="e2b7a-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="e2b7a-125">En plus de spécifier l’URI de métadonnées, vous devez également définir le niveau de confiance application sur complet. Cela permet à Exchange de représenter eux-mêmes et tout utilisateur autorisé du domaine.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="e2b7a-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2b7a-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="e2b7a-127">Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script figurant dans la documentation relative à l’authentification serveur et serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="e2b7a-128">Pour plus d’informations, reportez-vous à l’article [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenariat dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="e2b7a-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="e2b7a-129">Si vous avez correctement configuré des applications de partenariat pour Lync Server et Exchange, cela signifie que vous avez correctement configuré l’authentification de serveur à serveur entre les deux produits.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="e2b7a-130">Lync Server 2013 inclut une cmdlet Windows PowerShell, [test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), qui vous permet de vérifier que l’authentification de serveur à serveur est correctement configurée et que le service de stockage Lync Server peut se connecter à Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="e2b7a-131">Cette applet de commande permet de se connecter à la boîte aux lettres d’un utilisateur Exchange 2013, d’écrire un élément dans le dossier historique des conversations pour cet utilisateur, puis de supprimer cet élément éventuellement.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="e2b7a-132">Pour tester l’intégration de Lync Server 2013 et Exchange 2013, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e2b7a-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="e2b7a-133">Dans la commande précédente, le SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur Exchange 2013; Il n’existe pas de compte d’utilisateur valide pour votre commande.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="e2b7a-134">Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="e2b7a-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

