---
title: 'Lync Server 2013 : utilisation d’applets de commande pour inverser la préparation du domaine'
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
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Utilisation d’applets de commande pour inverser la préparation du domaine pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Utilisez l’applet de commande **Disable-CsAdDomain** pour inverser l’étape de préparation d’un domaine.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Pour utiliser des applets de commande afin d’inverser la préparation d’un domaine

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Par exemple :
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si le paramètre force est présent, la préparation du domaine est annulée, même si un ou plusieurs serveurs frontaux ou serveurs de conférence A/V dans le domaine sont activés. Si le paramètre force n’est pas présent, la préparation du domaine est restaurée si un serveur frontal ou un serveur de conférence A/V dans le domaine est activé.
    
    <div>
    

    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d'indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est caractéristique des déploiements de mise à niveau qui n'ont pas eu leur paramètre global migré vers le conteneur de configuration), vous définissez un contrôleur de domaine dans la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à n'&nbsp;importe quel contrôleur de domaine dans AD DS.

    
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

