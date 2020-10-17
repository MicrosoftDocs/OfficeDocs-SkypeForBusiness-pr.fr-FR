---
title: 'Lync Server 2013 : délégation des autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504281"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="2c9af-102">Déléguer les autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c9af-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c9af-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2c9af-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2c9af-104">Si vous ne souhaitez pas accorder l’appartenance au groupe administrateurs du domaine aux utilisateurs ou aux groupes qui déploient Lync Server 2013, vous pouvez permettre aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de commande Windows PowerShell **Enable-CsTopology**   sur les serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c9af-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="2c9af-105">Par défaut, les membres du groupe RTCUniversalServerAdmins n’ont pas la possibilité d’exécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="2c9af-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="2c9af-106">Vous accordez des droits et des autorisations d’administrateur pour exécuter **Enable-CsTopology** sur des serveurs exécutant Lync Server à l’aide de l’applet de commande **Grant-CsSetupPermission** et en spécifiant une unité d’organisation où se trouvent les objets ordinateur du serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c9af-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="2c9af-107">La préparation du domaine qui a lieu lors de l’installation de Lync Server n’ajoute pas automatiquement les autorisations qui permettent aux membres du groupe RTCUniversalServerAdmins d’exécuter la cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="2c9af-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="2c9af-108">Cela signifie que, par défaut, vous devez être administrateur de domaine pour activer une topologie.</span><span class="sxs-lookup"><span data-stu-id="2c9af-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="2c9af-109">Pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’activer une topologie, vous devez exécuter l’applet de commande Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="2c9af-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="2c9af-110">De plus, vous devrez exécuter cette applet de commande sur chaque conteneur Active Directory hébergeant des ordinateurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c9af-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="2c9af-111">Souvenez-vous que cette applet de commande n’accorde des autorisations qu’au groupe RTCUniversalServerAdmins. Il ne peut pas être utilisé pour accorder des autorisations à d’autres groupes de sécurité ou des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="2c9af-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c9af-112"><STRONG>Enable-CsTopology</STRONG> est l’applet de commande clé pour permettre aux membres du groupe RTCUniversalServerAdmins de configurer et de déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c9af-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="2c9af-113">Pour ajouter la possibilité d’exécuter Enable-CsTopology au groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2c9af-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="2c9af-114">Ouvrez une session sur un serveur en tant que membre du groupe administrateurs du domaine pour le domaine sur lequel l’utilisateur délégué exécutera **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="2c9af-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="2c9af-115">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c9af-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="2c9af-116">Lync Server 2013 Management Shell est automatiquement installé sur chaque serveur frontal ou sur tout ordinateur sur lequel les outils d’administration Lync Server 2013 ont été installés.</span><span class="sxs-lookup"><span data-stu-id="2c9af-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="2c9af-117">Pour plus d’informations sur Lync Server 2013 Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="2c9af-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="2c9af-118">Exécutez l’applet de commande suivante à partir de Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="2c9af-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c9af-119">Si l’unité d’organisation n’est pas de niveau supérieur, vous devez fournir le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="2c9af-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="2c9af-120">Dans l’exemple suivant, l’unité d’organisation est « Lync Servers », qui se trouve dans le domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2c9af-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

