---
title: Gestion des paramètres de configuration du service de journalisation centralisée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Gestion des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service de journalisation centralisée est contrôlé et configuré par les paramètres et les paramètres créés et utilisés par le contrôleur de service de journalisation centralisée (CLSController) pour envoyer des commandes à l’agent de service de journalisation centralisée de l’ordinateur individuel (CLSAgent). L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande Démarrer) utilise la configuration des scénarios, des fournisseurs, de la taille du journal, de la durée du suivi et des indicateurs pour commencer à collecter des journaux de suivi en fonction des informations de configuration fournies.

<div>


> [!IMPORTANT]
> Toutes les applets de commande Windows PowerShell répertoriées pour le service de journalisation centralisée ne sont pas conçues pour être utilisées avec des déploiements locaux de Lync Server 2013. Bien qu’ils semblent fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux de Lync Server 2013 : 
> <UL>
> <LI>
> <P><STRONG>Applets de commande CsClsRegion :</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>et <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Applets de commande CsClsSearchTerm :</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> et <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Applets de commande CsClsSecurityGroup :</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>et <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Les paramètres définis dans ces cmdlets n’entravent pas ou ne provoquent pas de comportement indésirable, mais ils sont conçus pour être utilisés avec Microsoft 365 et ne produisent pas les résultats attendus dans les déploiements locaux. Cela ne signifie pas qu’il n’est pas utilisé pour ces applets de commande dans des déploiements locaux, mais leur utilisation est une rubrique plus avancée qui n’est pas abordée dans cette documentation.


</div>

<div>

## <a name="in-this-section"></a>Dans cette section

Les rubriques de cette section définissent les options de configuration, les paramètres et les paramètres du service de journalisation centralisée. Les rubriques suivantes contiennent des informations sur la configuration du service de journalisation centralisée, la récupération des paramètres de configuration, la création de scénarios, la gestion des groupes de sécurité pour le service de journalisation centralisée, la recherche, etc.

  - [Gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configuration des fournisseurs pour le service de journalisation centralisée dans Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configuration des scénarios pour le service de journalisation centralisée dans Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets de journalisation centralisée dans Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

