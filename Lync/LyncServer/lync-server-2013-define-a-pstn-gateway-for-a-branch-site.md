---
title: 'Lync Server 2013 : Définition d’une passerelle RTC pour un site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="1ff86-102">Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff86-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff86-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1ff86-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1ff86-104">Procédez comme suit sur le site central, qui contient au moins un pool frontal ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="1ff86-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ff86-105">Avant d’effectuer cette procédure, les conditions suivantes doivent être en vigueur :</span><span class="sxs-lookup"><span data-stu-id="1ff86-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1ff86-106">Le logiciel de&nbsp;communications Lync Server 2013 doit être configuré sur le site central.</span><span class="sxs-lookup"><span data-stu-id="1ff86-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="1ff86-107">Le serveur de médiation doit être déployé sur le site central.</span><span class="sxs-lookup"><span data-stu-id="1ff86-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="1ff86-108">Pour définir une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="1ff86-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="1ff86-109">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1ff86-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1ff86-110">Dans l’arborescence de la console, développez le site central, développez **sites de succursales**, développez le nom du site de succursale pour lequel vous voulez définir une passerelle de réseau téléphonique commuté (RTC), puis développez **composants partagés**.</span><span class="sxs-lookup"><span data-stu-id="1ff86-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="1ff86-111">Cliquez avec le bouton droit sur **passerelles RTC**, puis cliquez sur **nouvelle passerelle IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1ff86-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="1ff86-112">Dans la boîte de dialogue **définir une nouvelle passerelle IP/PSTN** , cliquez sur **FQDN ou adresse IP de passerelle**, puis tapez le nom de domaine complet (FQDN) ou l’adresse IP de la passerelle que vous déployez sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="1ff86-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="1ff86-113">Cliquez sur **port d’écoute pour la passerelle RTC/IP**, puis acceptez les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="1ff86-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="1ff86-114">Dans la liste **protocole de transport SIP** , cliquez sur le protocole de transport utilisé par la passerelle, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ff86-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ff86-115">Pour des raisons de sécurité, nous vous recommandons vivement d’utiliser une passerelle RTC qui prend en charge le protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="1ff86-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="1ff86-116">Utilisez l’applet de cmdlet <STRONG>Set-CsPstnGateway</STRONG> pour modifier les propriétés d’une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ff86-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="1ff86-117">Pour plus d’informations, reportez-vous à la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>dans l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1ff86-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="1ff86-118">**Étape suivante** pour la résilience du site de succursale : [Configuration des utilisateurs pour la résilience du site de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="1ff86-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ff86-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ff86-119">See Also</span></span>


[<span data-ttu-id="1ff86-120">Options de déploiement de passerelle RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff86-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

