---
title: 'Lync Server 2013 : Délégation des autorisations de configuration'
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
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="92138-102">Délégation des autorisations de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92138-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92138-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="92138-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="92138-104">Si vous ne voulez pas attribuer l’appartenance au groupe administrateurs de domaine à des utilisateurs ou des groupes qui déploient Lync Server 2013, vous pouvez permettre aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de contrôle Windows PowerShell **Enable-CsTopology** sur des serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92138-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="92138-105">Par défaut, les membres du groupe RTCUniversalServerAdmins n’ont pas la possibilité d’exécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92138-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="92138-106">Vous pouvez accorder des droits d’administrateur et des autorisations pour exécuter **Enable-CsTopology** sur des serveurs exécutant Lync Server à l’aide de l’applet de passe **Grant-CsSetupPermission** et en spécifiant une unité d’organisation (UO) où les objets ordinateur exécutant Lync Server 2013 sont situés.</span><span class="sxs-lookup"><span data-stu-id="92138-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="92138-107">La préparation du domaine qui intervient lors de l’installation de Lync Server n’ajoute pas automatiquement les autorisations qui permettent aux membres du groupe RTCUniversalServerAdmins d’exécuter l’applet de demande Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="92138-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="92138-108">Cela signifie que, par défaut, vous devez être un administrateur de domaine pour pouvoir activer une topologie.</span><span class="sxs-lookup"><span data-stu-id="92138-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="92138-109">Pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’activer une topologie, vous devez exécuter l’applet de la cmdlet Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="92138-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="92138-110">Par ailleurs, vous devrez exécuter cette cmdlet sur chaque conteneur Active Directory qui héberge des ordinateurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92138-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="92138-111">Gardez à l’esprit que cette applet de cmdlet accorde uniquement des autorisations au groupe RTCUniversalServerAdmins ; l’applet de cmdlet ne peut pas être utilisée pour accorder des autorisations à d’autres groupes de sécurité ou à des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="92138-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92138-112"><STRONG>Enable-CsTopology</STRONG> est l’applet de clé pour permettre aux membres du groupe RTCUniversalServerAdmins de configurer et de déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92138-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="92138-113">Pour ajouter la possibilité d’exécuter Enable-CsTopology au groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="92138-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="92138-114">Connectez-vous à un serveur en tant que membre du groupe Domain Admins pour le domaine sur lequel l’utilisateur délégué exécutera **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="92138-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="92138-115">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="92138-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="92138-116">Lync Server 2013 Management Shell est automatiquement installé sur chaque serveur frontal ou sur tout ordinateur sur lequel sont installés les outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92138-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="92138-117">Pour plus d’informations sur Lync Server 2013 Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) dans la documentation opérations.</span><span class="sxs-lookup"><span data-stu-id="92138-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="92138-118">Exécutez l’applet de commande suivante à partir de Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="92138-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92138-119">Si l’unité d’organisation n’est pas de niveau supérieur, vous devez fournir le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="92138-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="92138-120">Dans l’exemple suivant, l’unité d’organisation est « Lync Servers », qui se trouve dans le domaine contoso.com.</span><span class="sxs-lookup"><span data-stu-id="92138-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

