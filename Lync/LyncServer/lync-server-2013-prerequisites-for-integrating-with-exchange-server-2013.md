---
title: 'Lync Server 2013 : prérequis pour l’intégration à Exchange Server 2013'
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
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="0e2fe-102">Conditions préalables à l’intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e2fe-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e2fe-103">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="0e2fe-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="0e2fe-104">Pour pouvoir intégrer Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, vous devez vous assurer que toutes les étapes préalables ont été effectuées.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="0e2fe-105">Comme vous pouvez vous attendre, l’intégration ne peut pas être effectuée tant que Exchange 2013 et Lync Server 2013 ne sont pas entièrement installés et en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="0e2fe-106">Pour plus d’informations sur l’installation d’Exchange, voir la documentation relative à [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)la planification et au déploiement d’Exchange 2013 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="0e2fe-107">Pour plus d’informations sur l’installation de Lync Server 2013, consultez la documentation [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)de planification et de déploiement à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="0e2fe-108">Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Lync Server 2013 et Exchange 2013. ces certificats permettent à Lync Server et Exchange d’échanger des informations et de communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="0e2fe-109">Lorsque vous installez Exchange 2013, un certificat auto-signé avec le nom Microsoft Exchange Server auth est créé pour vous.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="0e2fe-110">Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification serveur à serveur sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="0e2fe-111">Pour plus d’informations sur l’attribution de certificats dans Exchange 2013, voir « Configurer le flux de messagerie [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)et l’accès client » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="0e2fe-112">Pour Lync Server 2013, vous pouvez utiliser un certificat Lync Server existant comme certificat d’authentification de serveur à serveur. par exemple, vous pouvez également utiliser votre certificat par défaut comme certificat OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="0e2fe-113">Lync Server 2013 vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat d’authentification de serveur à serveur pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="0e2fe-114">le certificat inclue le nom de votre domaine SIP dans le champ Objet ;</span><span class="sxs-lookup"><span data-stu-id="0e2fe-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="0e2fe-115">le même certificat soit configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ;</span><span class="sxs-lookup"><span data-stu-id="0e2fe-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="0e2fe-116">la longueur du certificat soit d’au moins 2 048 bits.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="0e2fe-117">Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Microsoft Lync Server 2013, voir [affectation d’un certificat d’authentification de serveur à serveur à Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="0e2fe-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="0e2fe-118">Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="0e2fe-119">Dans Exchange 2013, le service de découverte automatique configure les profils utilisateur et donne accès aux services Exchange lorsque les utilisateurs ouvrent une session sur le système.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="0e2fe-120">Les utilisateurs indiquent leur adresse de messagerie et leur mot de passe au service de découverte automatique ; le service fournit en retour à l’utilisateur des informations telles que :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="0e2fe-121">Informations de connexion pour la connectivité interne et externe à Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="0e2fe-122">l’emplacement du serveur de boîte aux lettres de l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="0e2fe-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="0e2fe-123">les URL pour les fonctionnalités Outlook telles que les informations sur la disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion ;</span><span class="sxs-lookup"><span data-stu-id="0e2fe-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="0e2fe-124">les paramètres de serveur d’Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="0e2fe-125">Le service de découverte automatique doit être configuré pour pouvoir intégrer Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0e2fe-126">Vous pouvez vérifier si le service de découverte automatique a ou non été configuré en exécutant la commande suivante à partir d’Exchange Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="0e2fe-p106">Si cette valeur est vide, vous devez attribuer un URI au service de découverte automatique. Cet URI ressemble généralement à ceci :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="0e2fe-129">Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="0e2fe-130">Pour plus d’informations sur le service de découverte automatique, voir « présentation du service de [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)découverte automatique » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="0e2fe-131">Une fois le service de découverte automatique configuré, vous devez modifier les paramètres de configuration OAuth de Lync Server. Cela permet à Lync Server de savoir où trouver le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="0e2fe-132">Pour modifier les paramètres de configuration OAuth dans Lync Server 2013, exécutez la commande suivante à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="0e2fe-133">Lorsque vous exécutez cette commande, veillez à spécifier l’URI pour le service de découverte automatique qui s’exécute sur votre serveur Exchange, et que vous utilisez la **découverte automatique. svc** pour pointer sur l’emplacement du service au lieu de la **découverte automatique. xml** (qui pointe vers le fichier XML utilisé par le service).</span><span class="sxs-lookup"><span data-stu-id="0e2fe-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="0e2fe-134">Le paramètre Identity de la commande précédente est facultatif ; C’est parce que Lync Server vous permet uniquement d’avoir une collection globale unique de paramètres de configuration OAuth.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="0e2fe-135">Entre autres choses, cela signifie que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple :</span><span class="sxs-lookup"><span data-stu-id="0e2fe-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="0e2fe-136">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="0e2fe-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="0e2fe-p109">Si vous ne connaissez pas cette technologie, OAuth est un protocole d’autorisation standard utilisé par nombre des plus importants sites web. Grâce à OAuth, les informations d’identification et les mots de passe d’utilisateur ne sont pas transmis d’un ordinateur à un autre. L’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble de ressources spécifique pour une durée spécifique.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="0e2fe-140">En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e2fe-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="0e2fe-141">Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com résolu sur le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="0e2fe-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

