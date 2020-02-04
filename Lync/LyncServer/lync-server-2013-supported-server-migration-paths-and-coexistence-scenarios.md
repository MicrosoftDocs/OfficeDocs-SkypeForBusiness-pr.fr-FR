---
title: 'Lync Server 2013 : Chemins de migration de serveurs et scénarios de coexistence pris en charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Chemins de migration de serveurs et scénarios de coexistence pris en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Lync Server 2013 prend en charge la migration de l’un des éléments suivants :

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

La migration à partir d’un environnement exécutant ces deux versions précédentes n’est pas prise en charge. La migration de versions antérieures, comme Microsoft Office Communications Server 2007 ou Live Communications Server 2005, n’est pas prise en charge. Si votre déploiement précédent incluait une discussion de groupe, vous devez le faire séparément.

<div>

## <a name="migration-methods"></a>Méthodes de migration

La migration de tous les rôles serveur et topologies Lync Server est prise en charge. Vous pouvez effectuer une migration d’une topologie vers une autre topologie, y compris de Standard Edition Server vers Enterprise Edition Server.

Lync Server 2013 ne prend en charge que la méthode de migration suivante :

  - <span></span>  
    **Migration côte à côte.** Dans la migration côte à côte, Lync Server 2013 est déployé parallèlement à un déploiement Microsoft Lync Server 2010 ou Office Communications Server 2007 R2, puis transférez des opérations vers les nouveaux serveurs et déplacez les utilisateurs vers Lync Server 2013. Cette méthode nécessite des plateformes serveur supplémentaires, notamment du matériel et du logiciel, lors de la migration, et les noms de systèmes et de pools sont différents dans la nouvelle configuration. S’il est nécessaire de revenir à la version précédente, vous pouvez basculer les opérations sur les serveurs précédents.

La migration dans les forêts de services de domaine Active Directory n’est pas prise en charge.

Le chemin de migration recommandé est une approche progressive. Pour plus d’informations sur la migration à partir d’une version précédente, y compris la mise à l’exécution appropriée du déploiement des composants, voir les rubriques suivantes dans la documentation relative à la migration :

  - [Migration de Lync Server 2010 vers Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Scénarios de coexistence

Lync Server 2013 peut cohabiter avec les composants d’un déploiement de Lync Server 2010 ou d’un déploiement d’Office Communications Server 2007 R2. Le déploiement simultané de Lync Server 2013 avec Lync Server 2010 et Office Communications Server 2007 R2 (le déploiement simultané de ces trois versions) n’est pas pris en charge.

Dans le cadre d’une migration par phases dans laquelle un déploiement de Lync Server 2010 ou Office Communications Server 2007 R2 est le plus temporaire avec le nouveau déploiement Lync Server 2013, la prise en charge du routage de version mixte est limitée. Pour plus d’informations, voir la documentation relative à la migration.

Vous devez utiliser des ordinateurs distincts et distincts exécutant Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour vos instances de base de données Lync Server 2013. Vous ne pouvez pas utiliser la même instance de SQL Server pour une liste frontale Lync Server 2013 que vous utilisez pour une liste frontale Lync Server 2010 ou Office Communications Server 2007 R2. Si vous définissez et configurez Lync Server 2013 dans le générateur de topologie pour un déploiement qui dispose déjà de Lync Server 2010 ou d’Office Communications Server 2007 R2, le générateur de topologie n’autorise pas la définition d’une instance de Lync Server 2013 déjà utilisée dans la topologie.

Le générateur de topologie affiche le message suivant pour vous signaler ce problème : « le nom de domaine \[complet SQL Server du\] serveur contient déjà un rôle d’hébergement d’instances SQL ».

<div>


> [!NOTE]  
> Si vous envisagez de déployer des rôles de serveur nouveaux dans votre déploiement Lync Server 2013, vous devez commencer par mettre à niveau votre déploiement actuel comme décrit dans la documentation de migration et la documentation de déploiement, puis déployer les nouveaux rôles de serveur comme décrit dans documentation et documentation sur le déploiement de la planification. Si vous effectuez une migration à partir d’une version précédente de discussion de groupe, migrez-la en dernier, une fois que vous avez terminé le processus de migration de tous les autres composants de Lync Server 2010 ou Office Communications Server 2007 R2.



</div>

Pour plus d’informations sur les exigences de coexistence et sur les autres détails relatifs à la coexistence et à la migration de Lync Server 2010 ou d’Office Communications Server 2007 R2 et Lync Server 2013, reportez-vous à la rubrique [migration de Lync server 2010 vers Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) et [migration à partir d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) dans la documentation de migration. Pour plus d’informations sur la prise en charge des versions mixtes pour les clients, voir [clients pris en charge dans Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

