---
title: 'Lync Server 2013 : test de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b9aa12f7b3ae9b0c160147ad473976c92ab32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Test de récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-01-26_

Effectuez une récupération système pour un serveur de pool Lync Server 2013 afin de tester votre processus de récupération d’urgence documenté. Ce test simule une défaillance matérielle complète pour un serveur, et vous aide à garantir que les ressources, les plans et les données sont disponibles pour la récupération. Essayez de faire pivoter la sélection du test chaque mois afin que votre organisation teste l’échec à chaque fois d’un autre serveur ou d’un autre équipement.

Notez que le calendrier par lequel les organisations effectuent des tests de récupération d’urgence varient. Il est très important que les tests de récupération d’urgence ne soient pas ignorés ou négligés.

<div>


Exportez votre topologie, vos stratégies et vos paramètres de configuration Lync Server 2013 vers un fichier. Entre autres, ce fichier peut ensuite être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème est à l’issue d’une perte de données.

Importez votre topologie Lync Server 2013, vos stratégies et vos paramètres de configuration dans le magasin central de gestion ou sur l’ordinateur local comme illustré dans les commandes suivantes :

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Pour sauvegarder les données de production Lync Server 2013 :

  - Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données vers un fichier ou un périphérique de vidage de bande.

  - Utilisez une application de sauvegarde tierce pour sauvegarder les données dans un fichier ou sur une bande.

  - La cmdlet Export-applet csuserdata permet de créer une exportation XML de l’ensemble de la base de données RTC.

  - Utilisez la sauvegarde du système de fichiers ou une tierce partie pour sauvegarder le contenu et les journaux de conformité des réunions.

  - Utilisez l’outil en ligne de commande Export-CsConfiguration pour sauvegarder les paramètres Lync Server 2013.

La première étape de la procédure de basculement inclut un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.

Il s’agit d’un déplacement forcé car le pool de production n’est pas disponible pour accepter le déplacement de l’utilisateur.

Le processus de déplacement d’utilisateur Lync Server 2013 est en fait une modification apportée à un attribut sur l’objet de compte d’utilisateur en plus d’une mise à jour de l’enregistrement dans la base de données SQL RTC.

Ces données peuvent être restaurées à l’aide des deux processus suivants :

  - La base de données RTC peut être restaurée à partir du périphérique de vidage de sauvegarde d’origine à partir du serveur SQL de production à l’aide du processus de restauration standard de SQL Server ou à l’aide d’un utilitaire de sauvegarde/restauration tiers.

  - Les données de contact utilisateur peuvent être restaurées à l’aide de l’utilitaire DBIMPEXP. exe à l’aide du fichier XML qui a été créé à partir de l’exportation SQL Server de production.

Une fois ces données restaurées, les utilisateurs peuvent se connecter au pool Lync Server 2013 de récupération d’urgence et fonctionner normalement.

Pour permettre aux utilisateurs de se connecter au pool Lync Server 2013 de récupération d’urgence, une modification d’enregistrement DNS est requise.

Le pool de production Lync Server 2013 sera référencé par les clients à l’aide de la configuration automatique et des enregistrements SRV DNS suivants :

  - SRV : \_SIP. \_TLS. \<domaine\> /CNAME : SIP. \<Domain (domaine)\>

  - CNAME : SIP. \<domaine\> /CVC-pool-1. \<Domain (domaine)\>

Pour faciliter le basculement, cet enregistrement CNAMe doit être mis à jour pour référencer le nom de domaine complet du DROCSPool :

  - CNAME : SIP. \<domaine\> /DROCSPool. \<Domain (domaine)\>

  - SIP. \<Domain (domaine)\>

  - AV.\<Domain\>

  - webconf. \<Domain (domaine)\>

  - OCSServices. \<Domain (domaine)\>

<div>


> [!IMPORTANT]  
> Pour des procédures d’administration et de gestion détaillées, reportez-vous à la rubrique <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">sauvegarde et restauration de Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Applets de commande de sauvegarde et de haute disponibilité dans Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Sauvegarde et restauration de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

