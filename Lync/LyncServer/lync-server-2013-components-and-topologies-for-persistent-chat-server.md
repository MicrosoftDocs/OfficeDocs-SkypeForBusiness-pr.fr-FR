---
title: 'Lync Server 2013 : composants et topologies pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 320605ab363ff4879811873cc9ce957520b91b29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Composants et topologies pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le serveur de conversation permanente prend en charge les configurations à serveur unique et les configurations à plusieurs serveurs. Le serveur de conversation permanente peut également être exécuté sur un serveur Lync Server 2013 Standard Edition. Ces configurations sont constituées des topologies et des composants de serveur de conversation permanente suivants.

<div>

## <a name="persistent-chat-server-components"></a>Composants de serveur de conversation permanente

L’installation de la dernière version du serveur de conversation permanente nécessite les composants suivants :

  - Un ou plusieurs ordinateurs exécutant le serveur de conversation permanente et fournissant les services suivants :
    
      - Service de conversation permanente
    
      - Service de conformité, qui est activé si la conformité est activée
    
    <div>
    

    > [!IMPORTANT]  
    > Dans Lync Server 2013, les services Web de conversation permanente pour le chargement/téléchargement de fichiers sont colocalisés&nbsp;avec le serveur frontal Lync Server 2013.<BR>Les services Web de conversation permanente pour la gestion des salles de conversation sont également colocalisés avec le serveur frontal Lync Server 2013&nbsp;.

    
    </div>

  - Serveur (s) (plus d’un serveur en cas d’utilisation de la mise en miroir) qui héberge la base de données principale SQL Server pour héberger la base de données de contenu de conversation permanente où sont stockées le contenu, les salles et les catégories de la salle de conversation.
    
    <div>
    

    > [!NOTE]  
    > La base de données principale stocke des données d’historique de conversation, notamment des informations sur les catégories et les salles de conversation permanente créées.

    
    </div>

  - Si la conformité a été activée, un ou plusieurs serveurs (plusieurs serveurs en cas d’utilisation de la mise en miroir) qui hébergent la base de données principale SQL Server pour héberger la base de données de conformité de la conversation permanente, dans lequel sont stockés les événements de conformité et le contenu de conversation à des fins de conformité.

Pour administrer le serveur de conversation permanente à partir d’un ordinateur distinct (tel qu’une console d’administration), utilisez le panneau de configuration Lync Server sur l’ordinateur. Cet ordinateur doit ensuite être déployé dans un domaine des services de domaine Active Directory, avec au moins un serveur de catalogue global dans la racine de la forêt.

Pour plus d’informations sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente, voir [Technical Requirements for persistent Chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), supported [Hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server Software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prise en charge

Lync Server 2013 prend en charge un grand nombre de scénarios de colocalisation, ce qui vous permet d’économiser les coûts matériels en exécutant plusieurs composants sur un serveur (si vous avez une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si vous avez un grande organisation qui a besoin d’une évolutivité et de performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.

Le service de conformité de conversation permanente, si la conformité est activée, est colocalisé avec le serveur frontal Lync Server 2013.

Le serveur de conversation permanente peut être déployé sur le serveur Standard Edition. Le serveur principal du serveur de conversation permanente et la base de données de conformité de conversation permanente peuvent être colocalisés sur le serveur Standard Edition Server sur le serveur principal SQL Server Express local. Pour plus d’informations sur les composants qui peuvent être colocalisés, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

Pour Lync Server 2013 Enterprise Edition, les serveurs de conversation permanente ne peuvent pas être colocalisés sur le serveur Enterprise Edition. La base de données SQL Server pour le serveur de conversation permanente peut être colocalisée avec la base de données du serveur principal d’un pool frontal Enterprise Edition. La base de données SQL Server pour la conformité de la conversation permanente peut également être colocalisée avec la base de données du serveur principal d’un pool Enterprise Edition.

<div>


> [!IMPORTANT]  
> Le serveur qui héberge la base de données de conversation permanente peut héberger d’autres bases de données. Toutefois, lorsque vous considérez la base de données de conversation permanente avec d’autres bases de données, sachez que si vous stockez les messages de plus de quelques utilisateurs, l’espace disque nécessaire pour la base de données de conversation permanente peut augmenter considérablement. Pour cette raison, nous vous déconseillons de colocaliser la base de données de conversation permanente avec la base de données principale.



</div>

Si vous colocaliser la base de données de conversation permanente avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour une partie ou l’ensemble des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données, avec la limitation suivante :

  - Chaque instance de SQL Server ne peut contenir qu’une seule base de données principale et une seule base de données de conversation permanente.

Pour plus d’informations sur la colocalisation de tous les rôles serveur et bases de données, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologies de serveur de conversation permanente

Le serveur de conversation permanente prend en charge les topologies suivantes :

  - Lync Server 2013 Enterprise Edition serveur frontal de serveur de conversation permanente à serveur unique

  - Lync Server 2013 Enterprise Edition serveur frontal de serveur de conversation permanente à plusieurs serveurs

  - Serveur Lync Server 2013 Standard Edition avec SQL Server Express

  - Serveur Lync Server 2013 Standard Edition et serveur de conversation permanente sur un serveur distinct utilisant le serveur Standard Edition comme serveur du tronçon suivant.

Vous pouvez ajouter un serveur de conversation permanente à votre déploiement Lync Server 2013 à l’aide du générateur de topologie. Vous pouvez ajouter un serveur unique ou un pool de serveurs de conversation permanente de plusieurs serveurs à votre topologie.

<div>


> [!IMPORTANT]  
> Une fois que vous avez créé un pool de serveurs de conversation permanente avec un seul serveur à l’aide du générateur de topologie, vous ne pouvez pas ajouter de serveurs supplémentaires au pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologie à serveur unique

La configuration minimale et le déploiement le plus simple pour le serveur de conversation permanente est une seule topologie de serveur frontal de serveur de conversation permanente. Ce déploiement nécessite un serveur unique qui exécute le serveur de conversation permanente (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est requise, la base de données SQL Server pour stocker le données de conformité.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas ajouter d’autres serveurs à un pool de serveurs de conversation permanente qui est démarré en tant que déploiement à serveur unique dans le générateur de topologie. Nous vous recommandons d’utiliser la topologie de pool à plusieurs serveurs, même si vous utilisez un seul serveur, de manière à ce que vous puissiez ajouter d’autres serveurs par la suite si nécessaire.



</div>

La figure suivante illustre tous les composants requis et facultatifs d’une topologie pour un seul serveur frontal de serveur de conversation permanente avec conformité.

**Serveur de conversations permanentes unique**

![Topologie à serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à serveur unique avec service de conformité")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie à plusieurs serveurs

Pour augmenter la capacité et la fiabilité, vous pouvez déployer une topologie à plusieurs serveurs, comme décrit dans la rubrique [Planning for persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant un serveur de conversation permanente (les configurations de haute disponibilité et de récupération d’urgence autorisent jusqu’à huit, mais seulement quatre peuvent être actives et les quatre autres en attente). Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, soit un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs. Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, à ceci près que plusieurs serveurs hébergent le serveur de conversation permanente et peuvent être plus évolutifs. Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.

La figure suivante illustre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.

**Plusieurs serveurs de conversation permanente**

![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")

Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de conversation permanente communiquent et partagent des données. Par exemple, l’historique de la conversation qui a été initialement publié sur un service de conversation permanente est disponible à partir de n’importe quel service de conversation permanente dans le système. Tout service de conversation permanente peut accéder à un fichier téléchargé via un service de conversation permanente. Les utilisateurs peuvent être connectés à différents serveurs frontaux de serveur de conversation permanente et peuvent discuter et communiquer les uns avec les autres.

Le port par défaut TCP 8011 connecte un serveur à un pool de serveurs et est utilisé par le service de conversation permanente pour communiquer entre eux ou à des fins administratives.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

