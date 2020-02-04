---
title: 'Lync Server 2013 : configuration requise pour l’application Lync du Windows Store'
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
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="c8978-102">Configuration requise pour l’application Lync du Windows Store pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8978-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8978-103">_**Dernière modification de la rubrique :** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="c8978-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="c8978-104">Les organisations disposant d’un déploiement local de Lync Server doivent respecter les exigences suivantes pour prendre en charge l’application Lync du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="c8978-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8978-105">Pour Lync Server 2010, exécutez la mise à jour cumulative pour Lync Server 2010:2012 février (disponible à l’adresse suivante <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp: kbid = 2670352</A>) ou version ultérieure sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="c8978-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="c8978-106">Pour permettre aux utilisateurs de participer à des réunions, effectuez la mise à jour cumulative pour Lync Server 2010 : octobre 2012 (disponible à l’adresse suivante <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp: kbid = 2737915</A>) sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="c8978-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="c8978-107">Activez les services de découverte automatique, de Lync Web App et de ticket Web sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c8978-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="c8978-108">Activez l’authentification par certificat sur le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c8978-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="c8978-109">(Le processus d’inscription de l’utilisateur sur le serveur frontal ou le pool frontal est souvent désigné sous le nom d’bureau d’enregistrement.) Pour plus d’informations, consultez [créer des paramètres de configuration du Bureau d’enregistrement dans Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c8978-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="c8978-110">Publiez les enregistrements de ressource d’alias DNS (CNAMe) pour le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="c8978-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="c8978-111">Il n’est plus nécessaire de veiller à ce que le point de distribution de la liste de révocation de certificats (CDP) pour les certificats émis à Lync Server pointe vers une ressource HTTP au lieu d’une ressource LDAP.</span><span class="sxs-lookup"><span data-stu-id="c8978-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="c8978-112">Toutefois, assurez-vous que les ordinateurs client disposent des dernières mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="c8978-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="c8978-113">Configurer les serveurs proxy HTTP dans l’entreprise pour autoriser le trafic HTTP lié au serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="c8978-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="c8978-114">Ajoutez des exceptions pour les services de découverte automatique, Lync Web App et WebPart, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c8978-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="c8978-115">Sur les clients, installez Windows 8,1 et la version la plus récente de l’application Lync du Windows Store pour résoudre un problème de connexion qui se produit généralement lors de l’utilisation de plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur Edge est **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="c8978-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="c8978-116">Si votre organisation est inscrite au service Lync Online ou Office 365 et que vous utilisez votre propre nom de domaine, vous devez effectuer quelques étapes supplémentaires pour configurer votre réseau pour la découverte automatique des serveurs Lync.</span><span class="sxs-lookup"><span data-stu-id="c8978-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="c8978-117">La configuration requise pour la configuration réseau est la même pour l’application Lync du Windows Store et Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="c8978-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="c8978-118">Suivez les instructions "configurer votre réseau" dans l’article wiki Office 365 "configurer les appareils mobiles Lync" disponible à l’adresse [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="c8978-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c8978-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8978-119">See Also</span></span>


[<span data-ttu-id="c8978-120">Déploiement de l’application Lync du Windows Store dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8978-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

