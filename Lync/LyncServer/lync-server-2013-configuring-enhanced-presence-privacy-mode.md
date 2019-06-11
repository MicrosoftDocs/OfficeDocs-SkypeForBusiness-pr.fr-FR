---
title: 'Lync Server 2013: configuration du mode de confidentialité Enhanced presence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configuration du mode de confidentialité Enhanced presence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-12-08_

Le mode de confidentialité Enhanced presence permet aux utilisateurs de limiter les informations de présence de sorte qu’il ne soit visible que par les contacts répertoriés dans la liste de contacts Lync 2013. Les applets de commande **New-CsPrivacyConfiguration** et **Set-CsPrivacyConfiguration** disposent d’un paramètre EnablePrivacyMode Control de cette option. Lorsque EnablePrivacyMode est défini sur true, l’option permettant de limiter les informations de présence aux contacts devient disponible dans les options d’état de Lync 2013. Lorsque EnablePrivacyMode est défini sur false, les utilisateurs peuvent choisir de toujours autoriser tout le monde à voir leurs informations de présence ou à se conformer à toute modification ultérieure apportée par l’administrateur au mode de confidentialité.

<div>


> [!IMPORTANT]  
> Les paramètres de confidentialité de Lync 2013 et de Lync 2010 ne respectent pas les versions précédentes (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007). Si les versions précédentes d’Office Communicator sont autorisées à se connecter, l’état de l’utilisateur de Lync 2013, ses informations de contact ou son image peuvent être affichés par une personne qui n’a pas été autorisée à le consulter. De plus, les paramètres de confidentialité de l’utilisateur de Lync 2013 sont réinitialisés s’il se connecte par la suite à une version antérieure de Communicator.<BR>C’est pour ces raisons qu’il s’agit d’un scénario de migration avant d’activer le mode de confidentialité Enhanced PRESENCE: 
> <UL>
> <LI>
> <P>Assurez-vous que tous les utilisateurs disposent de Lync 2013.</P>
> <LI>
> <P>Définissez une règle de stratégie de version de client pour empêcher les versions précédentes de Communicator de se connecter.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Pour activer le mode de confidentialité Enhanced presence

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez la commande suivante :
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Cette commande active le mode de confidentialité pour tous les paramètres de configuration de confidentialité actuellement utilisés au sein de l’organisation. Pour plus d’informations sur la façon dont les configurations de la stratégie de fonctionnement du mode de confidentialité de Lync Server Enhanced s’adressent à la présence du contact pour le client Lync 2013, consultez l’article de la base de connaissances Microsoft [activation du mode de confidentialité de présence améliorée de Lync Server. État de certains contacts Lync en «indisponible»](http://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[Nouveau-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

