---
title: 'Lync Server 2013 : Utilisation d’applets de commande pour inverser la préparation d’un domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Utilisez l’applet de action **Disable-CsAdDomain** pour inverser l’étape de préparation du domaine.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Pour utiliser des applets de cmdlet pour contrepasser la préparation du domaine

1.  Ouvrez une session sur n’importe quel serveur du domaine en tant que membre du groupe Domain Admins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Par exemple :
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si le paramètre force est présent, la préparation du domaine est restaurée, même si un ou plusieurs serveurs frontaux ou serveurs de conférence A/V du domaine sont activés. Si le paramètre force n’est pas présent, la restauration de la préparation du domaine est arrêtée si un serveur frontal ou un serveur de conférence A/V du domaine est activé.
    
    <div>
    

    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer l’emplacement de stockage des paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (qui est généralement utilisé avec des déploiements de mise à niveau pour lesquels le paramètre global n’a pas été déplacé vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à tout&nbsp;contrôleur de domaine dans AD DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

