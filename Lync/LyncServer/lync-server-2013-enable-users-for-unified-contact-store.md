---
title: 'Lync Server 2013 : Activation des utilisateurs pour le magasin de contacts unifié'
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
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Vous n’avez pas besoin d’effectuer d’action supplémentaire pour activer le magasin de contacts unifié après le déploiement de Lync Server 2013. Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Pour activer les utilisateurs pour le magasin de contact unifié

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des opérations suivantes :
    
      - Pour activer globalement le magasin de contacts unifié pour tous les utilisateurs de Lync Server, sur la ligne de commande, tapez :
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Pour activer le magasin de contacts unifié pour les utilisateurs d’un site spécifique, dans la ligne de commande, tapez :
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Par exemple :
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Pour activer le magasin de contacts unifié par locataire, dans la ligne de commande, tapez :
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Par exemple :
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Pour activer le magasin de contacts unifié pour des utilisateurs spécifiques, sur la ligne de commande, tapez :
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.

        
        </div>
        
        Exemple :
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée <EM>Utilisateurs UCS activés</EM> avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

