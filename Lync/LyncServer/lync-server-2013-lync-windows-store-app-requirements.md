---
title: 'Lync Server 2013 : configuration requise pour les applications Lync Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3707c0074425411353a22b51d62251d33a4e31fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534601"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="fa6ee-102">Configuration requise pour les applications Lync Windows Store pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa6ee-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa6ee-103">_**Dernière modification de la rubrique :** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="fa6ee-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="fa6ee-104">Les organisations disposant d’un déploiement local de Lync Server doivent remplir les conditions suivantes pour prendre en charge l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa6ee-105">Pour Lync Server 2010, exécutez la mise à jour cumulative pour Lync Server 2010 : février 2012 (disponible à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) ou version ultérieure sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="fa6ee-106">Pour permettre aux utilisateurs de participer à des réunions, exécutez la mise à jour cumulative pour Lync Server 2010 : octobre 2012 (disponible à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="fa6ee-107">Activer le service de découverte automatique, Lync Web App et les services de ticket Web sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="fa6ee-108">Activez l’authentification par certificat sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="fa6ee-109">(Le processus d’enregistrement de l’utilisateur sur le serveur frontal ou le pool frontal est souvent appelé serveur d’inscriptions.) Pour plus d’informations, consultez la rubrique [créer des paramètres de configuration du serveur d’inscriptions dans Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fa6ee-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="fa6ee-110">Publiez les enregistrements de ressource d’alias DNS (CNAMe) pour le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="fa6ee-111">Il n’est plus nécessaire de s’assurer que le point de distribution de liste de révocation de certificats (CDP) pour les certificats délivrés à Lync Server pointe vers une ressource HTTP au lieu d’une ressource LDAP.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="fa6ee-112">Toutefois, assurez-vous que les mises à jour Windows les plus récentes sont installées sur les ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="fa6ee-113">Configurez des proxys HTTP dans l’entreprise pour autoriser le trafic HTTP associé à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="fa6ee-114">Ajoutez des exceptions pour les services de découverte automatique, Lync Web App et webticket, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="fa6ee-115">Sur les clients, installez Windows 8,1 et la dernière version de Lync Windows Store App pour résoudre un problème de connexion qui se produit généralement lorsque vous utilisez plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur Edge est **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="fa6ee-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="fa6ee-116">Si votre organisation s’abonne à Lync Online ou Microsoft 365 et que vous utilisez votre propre nom de domaine, vous devez suivre quelques étapes supplémentaires pour configurer votre réseau pour la découverte automatique des serveurs Lync.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-116">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="fa6ee-117">Les exigences de configuration réseau sont les mêmes pour les applications Lync Windows Store et Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="fa6ee-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fa6ee-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa6ee-118">See Also</span></span>


[<span data-ttu-id="fa6ee-119">Déploiement de l’application Lync Windows Store dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa6ee-119">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
