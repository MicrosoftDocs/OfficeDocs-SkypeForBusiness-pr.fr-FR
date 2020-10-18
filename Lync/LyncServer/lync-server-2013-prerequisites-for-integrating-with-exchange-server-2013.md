---
title: 'Lync Server 2013 : conditions requises pour l’intégration à Exchange Server 2013'
description: 'Lync Server 2013 : conditions préalables à l’intégration à Exchange Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5872fe3ec546997cd0633383fdda7e0549bec83f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579850"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="509e3-103">Conditions préalables à l’intégration de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="509e3-103">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="509e3-104">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="509e3-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="509e3-105">Avant de pouvoir intégrer Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, vous devez vous assurer que toutes les étapes préalables ont été effectuées.</span><span class="sxs-lookup"><span data-stu-id="509e3-105">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="509e3-106">Comme vous pouvez vous y attendre, l’intégration ne peut avoir lieu que lorsque Exchange 2013 et Lync Server 2013 sont entièrement installés et en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="509e3-106">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="509e3-107">Pour plus d’informations sur l’installation d’Exchange, consultez la documentation sur la planification et le déploiement d’Exchange 2013 à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) .</span><span class="sxs-lookup"><span data-stu-id="509e3-107">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="509e3-108">Pour plus d’informations sur l’installation de Lync Server 2013, voir la documentation sur la planification et le déploiement à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) .</span><span class="sxs-lookup"><span data-stu-id="509e3-108">For details about installing Lync Server 2013, see the planning and deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="509e3-109">Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Lync Server 2013 et à Exchange 2013 ; ces certificats permettent à Lync Server et Exchange d’échanger des informations et de communiquer les uns avec les autres.</span><span class="sxs-lookup"><span data-stu-id="509e3-109">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="509e3-110">Lorsque vous installez Exchange 2013, un certificat auto-signé avec le nom certificat d’authentification Microsoft Exchange Server est créé pour vous.</span><span class="sxs-lookup"><span data-stu-id="509e3-110">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="509e3-111">Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="509e3-111">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="509e3-112">Pour plus d’informations sur l’attribution de certificats dans Exchange 2013, voir « Configurer le flux de messagerie et l’accès au client » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) .</span><span class="sxs-lookup"><span data-stu-id="509e3-112">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="509e3-113">Pour Lync Server 2013, vous pouvez utiliser un certificat Lync Server existant comme certificat d’authentification de serveur à serveur ; par exemple, votre certificat par défaut peut également être utilisé comme certificat OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="509e3-113">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="509e3-114">Lync Server 2013 vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat pour l’authentification de serveur à serveur, à condition que :</span><span class="sxs-lookup"><span data-stu-id="509e3-114">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="509e3-115">Le certificat inclut le nom de votre domaine SIP dans le champ Subject.</span><span class="sxs-lookup"><span data-stu-id="509e3-115">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="509e3-116">Le même certificat est configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="509e3-116">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="509e3-117">Le certificat a une longueur d’au moins 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="509e3-117">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="509e3-118">Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Microsoft Lync Server 2013, reportez-vous [à la rubrique Assigning a Server-to-Server Authentication Certificate to Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="509e3-118">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="509e3-119">Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="509e3-119">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="509e3-120">Dans Exchange 2013, le service de découverte automatique configure les profils utilisateur et permet d’accéder aux services Exchange lorsque les utilisateurs se connectent au système.</span><span class="sxs-lookup"><span data-stu-id="509e3-120">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="509e3-121">Les utilisateurs présentent le service de découverte automatique avec leur adresse de messagerie et leur mot de passe ; en retour, les services fournissent à l’utilisateur des informations telles que :</span><span class="sxs-lookup"><span data-stu-id="509e3-121">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="509e3-122">Les informations de connexion pour la connectivité interne et externe à Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="509e3-122">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="509e3-123">Emplacement du serveur de boîtes aux lettres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="509e3-123">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="509e3-124">URL pour les fonctionnalités Outlook telles que les informations de disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="509e3-124">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="509e3-125">Paramètres du serveur Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="509e3-125">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="509e3-126">Le service de découverte automatique doit être configuré pour pouvoir intégrer Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="509e3-126">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="509e3-127">Vous pouvez vérifier si le service de découverte automatique a été configuré en exécutant la commande suivante à partir de l’environnement de commande Exchange Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :</span><span class="sxs-lookup"><span data-stu-id="509e3-127">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="509e3-128">Si cette valeur est vide, vous devez affecter un URI au service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="509e3-128">If this value is blank, you must assign a URI to the autodiscover service.</span></span> <span data-ttu-id="509e3-129">En règle générale, cet URI ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="509e3-129">Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="509e3-130">Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="509e3-130">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="509e3-131">Pour plus d’informations sur le service de découverte automatique, voir « Understanding the Autodiscover Service » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) .</span><span class="sxs-lookup"><span data-stu-id="509e3-131">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="509e3-132">Une fois que le service de découverte automatique a été configuré, vous devez modifier les paramètres de configuration OAuth de Lync Server ; Cela garantit que Lync Server sait où trouver le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="509e3-132">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="509e3-133">Pour modifier les paramètres de configuration OAuth dans Lync Server 2013, exécutez la commande suivante à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="509e3-133">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="509e3-134">Lors de l’exécution de cette commande, vérifiez que vous spécifiez l’URI pour le service de découverte automatique qui s’exécute sur votre serveur Exchange et que vous utilisez **autodiscover. svc** pour pointer vers l’emplacement du service au lieu de **autodiscover.xml** (pointant vers le fichier XML utilisé par le service) :</span><span class="sxs-lookup"><span data-stu-id="509e3-134">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="509e3-135">Le paramètre Identity de la commande précédente est facultatif ; Cela est dû au fait que Lync Server vous permet d’avoir une seule collection globale de paramètres de configuration OAuth.</span><span class="sxs-lookup"><span data-stu-id="509e3-135">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="509e3-136">Cela signifie, entre autres, que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple :</span><span class="sxs-lookup"><span data-stu-id="509e3-136">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="509e3-137">Set-applet csoauthconfiguration – ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "</span><span class="sxs-lookup"><span data-stu-id="509e3-137">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="509e3-138">Si vous n’êtes pas familiarisé avec cette technologie, OAuth est un protocole d’autorisation standard utilisé par un certain nombre de sites principaux.</span><span class="sxs-lookup"><span data-stu-id="509e3-138">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites.</span></span> <span data-ttu-id="509e3-139">Avec OAuth, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="509e3-139">With OAuth, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="509e3-140">Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.</span><span class="sxs-lookup"><span data-stu-id="509e3-140">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="509e3-141">En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="509e3-141">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="509e3-142">Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com qui se traduit par le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="509e3-142">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

