---
title: 'Lync Server 2013 : chemins de migration de serveurs et scénarios de coexistence pris en charge'
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
ms.openlocfilehash: 5ace33bad5d00dae398557acb66af6bdf880909b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Chemins de migration de serveurs et scénarios de coexistence pris en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Lync Server 2013 prend en charge la migration à partir de l’un des éléments suivants :

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

La migration à partir d’un environnement exécutant ces deux versions précédentes n’est pas prise en charge. La migration à partir de versions antérieures, telles que Microsoft Office Communications Server 2007 ou Live Communications Server 2005, n’est pas prise en charge. Si votre déploiement précédent comprenait la conversation de groupe, vous devez la migrer séparément.

<div>

## <a name="migration-methods"></a>Méthodes de migration

La migration de toutes les topologies Lync Server et des rôles serveur est prise en charge. Vous pouvez effectuer la migration d’une topologie vers une autre, par exemple du serveur Standard Edition vers le serveur Enterprise Edition.

Lync Server 2013 prend uniquement en charge la méthode de migration suivante :

  - <span></span>  
    **Migration côte à côte.** Dans une migration côte à côte, Lync Server 2013 est déployé parallèlement à un déploiement existant de Microsoft Lync Server 2010 ou d’Office Communications Server 2007 R2, puis vous transférez des opérations vers les nouveaux serveurs et déplacez les utilisateurs vers Lync Server 2013. Cette méthode nécessite des plateformes de serveur supplémentaires, y compris le matériel et les logiciels, pendant la migration, et les noms de système et de pool sont différents dans la nouvelle configuration. S’il s’avère nécessaire de revenir à la version précédente, vous pouvez basculer les opérations vers les serveurs précédents.

La migration dans les forêts des services de domaine Active Directory n’est pas prise en charge.

L’option de migration recommandée est de procéder par phase. Pour plus d’informations sur la migration à partir d’une version précédente, y compris sur les phases de déploiement de composants appropriées, voir les rubriques suivantes dans la documentation de migration :

  - [Migration de Lync Server 2010 vers Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, Serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Scénarios de coexistence

Lync Server 2013 peut coexister avec les composants d’un déploiement Lync Server 2010 ou d’un déploiement Office Communications Server 2007 R2. Le déploiement simultané de Lync Server 2013 avec Lync Server 2010 et Office Communications Server 2007 R2 (déploiement simultané de ces trois versions) n’est pas pris en charge.

Lors d’une migration progressive dans laquelle un déploiement Lync Server 2010 ou Office Communications Server 2007 R2 précédent coexiste temporairement avec le nouveau déploiement Lync Server 2013, la prise en charge du routage de version mixte est limitée. Pour plus d’informations, voir la documentation de migration.

Vous devez utiliser des ordinateurs distincts et distincts exécutant Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour vos instances de base de données Lync Server 2013. Vous ne pouvez pas utiliser la même instance de SQL Server pour un pool frontal Lync Server 2013 que vous utilisez pour un pool frontal Lync Server 2010 ou Office Communications Server 2007 R2. Si vous définissez et configurez Lync Server 2013 dans le générateur de topologie pour un déploiement sur lequel Lync Server 2010 ou Office Communications Server 2007 R2 est déjà déployé, le générateur de topologies ne vous permet pas de définir une instance d’un Lync Server 2013 déjà utilisé dans la topologie.

Le générateur de topologie affiche le message suivant pour vous informer de ce problème : « le nom de \[domaine complet SQL Server\] du serveur contient déjà une instance SQL qui héberge le rôle «magasin d’utilisateurs ».»

<div>


> [!NOTE]  
> Si vous avez l’intention de déployer des rôles de serveur qui sont nouveaux dans votre déploiement Lync Server 2013, vous devez d’abord mettre à niveau votre déploiement existant comme décrit dans la documentation de migration et la documentation de déploiement, puis déployer les nouveaux rôles serveur comme décrit dans la documentation de planification et la documentation de déploiement. Si vous migrez une version antérieure de la conversation de groupe, migrez-la en dernier, après avoir terminé le processus de migration de tous les autres composants depuis Lync Server 2010 ou Office Communications Server 2007 R2.



</div>

Pour obtenir des exigences spécifiques en matière de coexistence et d’autres détails sur la coexistence et la migration des composants Lync Server 2010 ou Office Communications Server 2007 R2 et Lync Server 2013, consultez la rubrique [migration de Lync server 2010 vers Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) et [migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) dans la documentation de migration. Pour plus d’informations sur la prise en charge des versions mixtes pour les clients, consultez la rubrique [clients pris en charge dans les déploiements précédents dans Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

