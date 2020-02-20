---
title: 'Lync Server 2013 : configuration du mode de confidentialité améliorée de la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91326778777e6ddd1db2f8938cfb78e96ed8c7f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configuration du mode de confidentialité améliorée de la présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-08_

Grâce au mode de confidentialité de la présence enrichie, les utilisateurs peuvent restreindre leur information de présence afin qu’ils soient visibles uniquement par les contacts répertoriés dans la liste de contacts Lync 2013. Les cmdlets **New-CsPrivacyConfiguration** et **Set-CsPrivacyConfiguration** ont un paramètre EnablePrivacyMode contrôle cette option. Lorsque EnablePrivacyMode est défini sur true, l’option de restriction des informations de présence aux contacts devient disponible dans les options d’état de Lync 2013. Lorsque l’option EnablePrivacyMode est définie sur False, les utilisateurs peuvent choisir de toujours autoriser les utilisateurs à consulter leurs informations de présence ou d’accepter toutes les futures modifications que l’administrateur apporte au mode de confidentialité.

<div>


> [!IMPORTANT]  
> Les paramètres de confidentialité de Lync 2013 et Lync 2010 ne sont pas honorés par les versions antérieures (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007). Si les versions précédentes d’Office Communicator sont autorisées à se connecter, le statut de l’utilisateur Lync 2013, les informations de contact ou l’image peuvent être affichés par une personne qui n’a pas été autorisée à l’afficher. De plus, les paramètres de confidentialité de l’utilisateur Lync 2013 sont réinitialisés s’il se connecte ultérieurement à l’aide d’une version précédente de Communicator.<BR>Pour ces raisons, dans un scénario de migration, avant de pouvoir activer le mode de confidentialité améliorée de la présence : 
> <UL>
> <LI>
> <P>Assurez-vous que Lync 2013 est installé sur chaque utilisateur.</P>
> <LI>
> <P>Définissez une règle de stratégie de version de client empêchant les versions précédentes de Communicator de se connecter.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Pour activer le mode de confidentialité améliorée de la présence

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la commande suivante :
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Cette commande active le mode confidentialité pour tous les paramètres de confidentialité utilisés actuellement dans votre entreprise. Pour plus d’informations sur la façon dont les configurations de stratégie de mode de confidentialité de la présence améliorée de Lync Server gère la présence du contact pour le client Lync 2013, voir l’article de la base de connaissances Microsoft [activation du mode de confidentialité Enhanced presence de Lync Server met à jour l’état de présence de certains contacts Lync sur « indisponible »](https://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

