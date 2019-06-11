---
title: Gestion des paramètres de configuration du service de journalisation centralisé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Gestion des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Le service de journalisation centralisé est contrôlé et configuré à l’aide de paramètres et de paramètres créés et utilisés par le contrôleur de service de journalisation centralisé (CLSController) pour envoyer des commandes à l’agent de service de journalisation centralisé de l’ordinateur ( CLSAgent). L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande de démarrage) utilise la configuration des scénarios, fournisseurs, taille du journal, durée du suivi et indicateurs pour commencer à collecter des journaux de suivi conformément aux informations de configuration fournies.

<div>


> [!IMPORTANT]
> Les applets de connexion Windows PowerShell n’ayant pas été répertoriées pour le service de journalisation centralisée sont conçues pour une utilisation avec des déploiements sur site de Lync Server 2013. Même si cela semble fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux de Lync Server 2013: 
> <UL>
> <LI>
> <P><STRONG>Cmdlets CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>et <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Cmdlets CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> et <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Cmdlets CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>et <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Les paramètres définis dans ces cmdlets n’entravent pas ou risquent de provoquer un comportement indésirable, mais ils sont conçus pour une utilisation avec Microsoft Office 365 et ne produiront pas les résultats attendus dans les déploiements sur site. Ce n’est pas qu’il n’y a aucune utilisation pour ces applets de configuration dans les déploiements sur site, mais leur utilisation est un sujet plus avancé qui n’est pas abordé dans cette documentation.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

Les rubriques de cette section définissent les options de configuration, les paramètres et les paramètres du service de journalisation centralisé. Pour plus d’informations sur la configuration du service de journalisation centralisé, la façon de récupérer les paramètres de configuration, la création de scénarios, la gestion des groupes de sécurité pour le service de journalisation centralisé, la recherche, etc., est contenue dans les rubriques suivantes.

  - [Gestion de l’ordinateur, du site et de la configuration du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configuration de fournisseurs pour le service de journalisation centralisé dans Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configuration de scénarios pour le service de journalisation centralisé dans Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Présentation du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets d’enregistrement centralisé dans Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

