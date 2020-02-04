---
title: 'Lync Server 2013 : composants et topologies pour le serveur de chat permanent'
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
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Composants et topologies pour le serveur de chat permanent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Le serveur Chat permanent prend en charge les configurations à serveur unique et les configurations à plusieurs serveurs. Le serveur de chat permanent peut également être exécuté sur un serveur Lync Server 2013 Standard Edition Server. Ces configurations se composent des topologies et composants serveur de chat permanent suivants.

<div>

## <a name="persistent-chat-server-components"></a>Composants serveur de chat permanent

Pour installer la dernière version de Chat Server, vous devez disposer des éléments suivants :

  - Un ou plusieurs ordinateurs exécutant un serveur Chat permanent et fournissant les services suivants :
    
      - Service Chat permanent
    
      - Service de conformité, activé si la conformité est activée
    
    <div>
    

    > [!IMPORTANT]  
    > Dans Lync Server 2013, les services Web chat permanent pour le chargement et le téléchargement de fichiers sont désormais colocalisés avec le serveur frontal de Lync Server 2013&nbsp;.<BR>Les services Web chat permanent pour la gestion des salles de conversation sont également colocalisés avec le serveur frontal Lync Server 2013&nbsp;.

    
    </div>

  - Serveur (s) (plusieurs serveurs si la mise en miroir est utilisée) qui héberge la base de données principale SQL Server pour l’hébergement de la base de données de contenu de conversation permanente où le contenu, les salles et les catégories de salle de conversation sont stockés.
    
    <div>
    

    > [!NOTE]  
    > La base de données principale stocke les données de l’historique des conversations, y compris les informations sur les catégories et les salles de conversation permanentes qui sont créées.

    
    </div>

  - Si la conformité a été activée, un ou plusieurs serveurs (serveur si la mise en miroir est utilisé) qui héberge la base de données principale SQL Server pour l’hébergement de la base de données de compatibilité des conversations permanentes, où les événements de conformité et le contenu des discussions sont stockés dans le cadre de la conformité.

Pour administrer le serveur de chat permanent depuis un autre ordinateur (par exemple, une console d’administration), utilisez le panneau de configuration de Lync Server sur l’ordinateur. Cet ordinateur doit ensuite être déployé dans un domaine AD FS (Active Directory Domain Services), avec au moins un serveur de catalogue global dans la racine de la forêt.

Pour plus d’informations sur les configurations matérielles et logicielles requises pour le serveur de chat permanent, voir [configuration logicielle requise pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md)et [prise en charge de l’infrastructure et des logiciels serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation relative à la prise en charge.

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prises en charge

Lync Server 2013 prend en charge un large éventail de scénarios de colocalisation, qui vous permettent de gagner en souplesse en exécutant plusieurs composants sur un serveur (si vous disposez d’une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si vous disposez d’un compte grande organisation nécessitant une évolutivité et des performances optimales. Prenez en compte les facteurs d’évolutivité avant de décider de collocater ou non les composants.

Le service de Compliance chat permanent, si la conformité est activée, est colocalisé sur le serveur frontal de Lync Server 2013.

Le serveur de chat permanent peut être déployé sur un serveur Standard Edition Server. Le serveur principal de chat de chat serveur et la base de données de conformité des conversations permanentes peuvent être colocalisées sur le serveur Standard Edition Server du serveur principal SQL Server Express local. Pour plus d’informations sur les composants qui peuvent être colocalisés à partir de cet emplacement, voir [prise en charge de la coexistence du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de support.

Pour Lync Server 2013 Enterprise Edition, les serveurs de chat permanent ne peuvent pas être colocalisés sur le serveur Enterprise Edition. La base de données SQL Server pour le serveur de chat permanent peut être colocalisée avec la base de données serveur principal d’un pool frontal Enterprise Edition. La base de données SQL Server pour la conformité à la conversation permanente peut également être colocalisée avec la base de données serveur dorsal d’un pool Enterprise Edition.

<div>


> [!IMPORTANT]  
> Le serveur qui héberge la base de données de chat permanent peut héberger d’autres bases de données. Toutefois, si vous envisagez de collocating la base de données de chat persistante avec d’autres bases de données, n’ayez pas besoin d’augmenter la taille de la base de données de chat persistante. C’est pourquoi nous vous déconseillons de collocating la base de données de chat persistante avec la base de données principale.



</div>

Si vous collocate la base de données de chat permanent avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour tout ou partie des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données, avec la limite suivante :

  - Chaque instance de SQL Server peut contenir uniquement une seule base de données principale et une seule base de données de conversation permanente.

Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologies serveur de chat permanent

Le serveur Chat permanent prend en charge les topologies suivantes :

  - Lync Server 2013 Enterprise Edition serveur unique de chat serveur serveur principal

  - Lync Server 2013 Enterprise Edition serveur multiserveur de chat permanent serveur serveur principal

  - Lync Server 2013 Standard Edition Server avec SQL Server Express

  - Lync Server 2013 Standard Edition Server et serveur de chat permanent sur un serveur distinct utilisant Standard Edition Server comme serveur de tronçon suivant.

Vous pouvez ajouter le serveur de chat permanent à votre déploiement de Lync Server 2013 à l’aide du générateur de topologie. Vous pouvez ajouter un serveur unique ou un pool de serveurs de chat permanent multiples à votre topologie.

<div>


> [!IMPORTANT]  
> Après avoir créé un pool de serveurs de chat permanent avec un serveur unique à l’aide du générateur de topologie, vous ne pouvez pas ajouter de serveurs supplémentaires au pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologie à serveur unique

La configuration minimum et le déploiement le plus simple pour le serveur de chat permanent est une topologie de serveur frontal de chat permanent unique. Ce déploiement nécessite un serveur unique exécutant chat permanent (qui exécute éventuellement le service de conformité, si la conformité est activée), un serveur qui héberge la base de données SQL Server et si la conformité est requise, la base de données SQL Server pour stocker le données de conformité.

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de chat permanent démarré comme déploiement d’un serveur unique dans le générateur de topologie. Nous vous recommandons d’utiliser la topologie de pool multiserveur, même si vous utilisez un serveur unique, afin que vous puissiez ajouter d’autres serveurs ultérieurement, si nécessaire.



</div>

La figure suivante montre tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontal de chat permanent avec conformité.

**Serveur de chat permanent unique**

![Topologie de serveur unique avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie de serveur unique avec service de conformité")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie de plusieurs serveurs

Afin d’offrir une plus grande capacité et une fiabilité accrue, vous pouvez déployer une topologie multiserveur, comme décrit dans [planification pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie multiserveur peut inclure jusqu’à quatre ordinateurs actifs exécutant chat permanent (les configurations de haute disponibilité et de récupération d’urgence peuvent prendre jusqu’à 8, mais seules quatre peuvent être actives et les quatre autres en veille). Chaque serveur peut prendre en charge autant d’utilisateurs simultanés qu' 20 000, soit un total d' 80 000 utilisateurs simultanés connectés à un pool de serveurs de chat permanent doté de 4 serveurs. Une topologie multiserveur est la même que celle de la topologie sur un serveur, à l’exception de l’hébergement de plusieurs serveurs et de la possibilité d’augmenter leur taille. Plusieurs ordinateurs exécutant un serveur Chat permanent doivent résider dans le même domaine de services de domaine Active Directory que Lync Server et le service de conformité.

La figure suivante montre tous les composants d’une topologie multiserveur avec plusieurs ordinateurs exécutant une conversation permanente serveur, le service de conformité facultatif et une base de données de conformité séparée.

**Plusieurs serveurs de chat permanent**

![Topologie de plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie de plusieurs serveurs")

Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de chat permanent communiquent et partagent des données. Par exemple, l’historique des discussions publié à l’origine dans un service de chat permanent est disponible à partir de n’importe quel service de chat permanent du système. Un service de chat permanent peut accéder à un fichier téléchargé par le biais d’un service de chat permanent. Les utilisateurs peuvent se connecter à différents serveurs front-end serveur de chat permanent et communiquer entre eux.

Le port TCP 8011 par défaut connecte un serveur à un pool de serveurs et est utilisé par le service de chat permanent pour communiquer entre eux ou à des fins d’administration.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

