---
title: 'Lync Server 2013 : activation des utilisateurs pour le magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b4c060cfce4e45f4736abcbc0d4c9d02b1abc1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528551"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="84efb-102">Activer les utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84efb-102">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84efb-103">_**Dernière modification de la rubrique :** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="84efb-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="84efb-104">Lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="84efb-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="84efb-105">Aucune action supplémentaire n’est nécessaire pour activer le magasin de contacts unifié après avoir déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84efb-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="84efb-106">Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible.</span><span class="sxs-lookup"><span data-stu-id="84efb-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="84efb-107">Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="84efb-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="84efb-108">Pour activer les utilisateurs pour le magasin de contact unifié</span><span class="sxs-lookup"><span data-stu-id="84efb-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="84efb-109">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="84efb-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="84efb-110">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="84efb-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="84efb-111">Pour activer le magasin de contacts unifié globalement pour tous les utilisateurs de Lync Server, à partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="84efb-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="84efb-112">Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="84efb-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="84efb-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="84efb-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="84efb-114">Pour activer le magasin de contact unifié par locataire, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="84efb-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="84efb-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="84efb-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="84efb-116">Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="84efb-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="84efb-117">Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84efb-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="84efb-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="84efb-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="84efb-p102">Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée <EM>Utilisateurs UCS activés</EM> avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.</span><span class="sxs-lookup"><span data-stu-id="84efb-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

