---
title: Configurer une entrée d’application approuvée pour le contrôle d’appel distant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43921fcdeb5ca6e5c74e2c7a82b36bf830cbaa15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="c22ee-102">Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c22ee-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c22ee-103">_**Dernière modification de la rubrique :** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="c22ee-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="c22ee-104">La passerelle SIP/CSTA doit être configurée en tant qu’application approuvée afin de permettre à Lync Server d’appliquer un itinéraire statique pour acheminer les appels vers la passerelle.</span><span class="sxs-lookup"><span data-stu-id="c22ee-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c22ee-105">Si vous migrez des utilisateurs à partir d’une version précédente du déploiement Lync Server, veillez à supprimer toutes les entrées d’applications approuvées existantes (précédemment connues sous le nom d’entrées d’hôte autorisé) créées pour la passerelle SIP/CSTA avant de suivre les procédures décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c22ee-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="c22ee-106">Pour plus d’informations, consultez <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">la rubrique supprimer un hôte autorisé hérité dans Lync Server 2013 (facultatif)</A>.</span><span class="sxs-lookup"><span data-stu-id="c22ee-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="c22ee-107">Si vous envisagez de déployer un nouveau contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez vérifier que la <STRONG>limite d’utilisation des services aux adresses IP sélectionnées</STRONG> doit être définie sur des pools et des applications approuvées existantes, si vous voulez utiliser le même port TCP pour la nouvelle application approuvée.</span><span class="sxs-lookup"><span data-stu-id="c22ee-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="c22ee-108">Pour configurer une entrée d’application approuvée pour la passerelle SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="c22ee-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="c22ee-109">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle RBAC (contrôle d’accès basé sur un rôle) auquel vous avez affecté la cmdlet **New-CsTrustedApplicationPool** .</span><span class="sxs-lookup"><span data-stu-id="c22ee-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="c22ee-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c22ee-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c22ee-111">Pour créer une entrée d’application approuvée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c22ee-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="c22ee-112">Pour une connexion TLS (Transport Layer Security), tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="c22ee-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c22ee-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="c22ee-114">Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="c22ee-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c22ee-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="c22ee-116">Pour ajouter l’application approuvée au pool, procédez de l’une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="c22ee-117">Pour une connexion TLS, tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="c22ee-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c22ee-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="c22ee-119">Pour une connexion TCP, tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="c22ee-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c22ee-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="c22ee-121">Pour implémenter les modifications publiées que vous avez apportées à la topologie, tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="c22ee-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c22ee-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c22ee-122">See Also</span></span>


[<span data-ttu-id="c22ee-123">Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c22ee-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="c22ee-124">Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c22ee-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

