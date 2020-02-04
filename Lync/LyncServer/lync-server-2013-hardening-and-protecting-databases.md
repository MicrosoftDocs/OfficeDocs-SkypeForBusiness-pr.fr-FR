---
title: 'Lync Server 2013 : renforcement et protection des bases de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Renforcement et protection des bases de données de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-05_

Microsoft Lync Server 2013 dépend également de bases de données SQL Server pour le stockage des informations utilisateur, de l’état de conférences, des données d’archivage et des enregistrements des détails des appels. Vous pouvez optimiser la disponibilité des données Lync Server 2013 sur les bases de données principales de Lync Server en partitionnant les données d’application d’une façon qui améliore la tolérance de panne et simplifie la résolution des problèmes. Pour ce faire, vous pouvez partitionner les données d’application de la façon suivante :

  - **L’utilisation de meilleures pratiques**   de partitionnement de serveur permet de séparer les fichiers de votre système d’exploitation, de l’application et du programme de vos fichiers de données.

  - **Le stockage des fichiers journaux des transactions et des fichiers**   de base de données stocke ces fichiers séparément pour améliorer la tolérance de panne et optimiser la récupération, et les stocker sur un disque ou un volume chiffré.

  - **L’utilisation**   de clusters de serveurs pour mettre en cluster les serveurs principaux pour optimiser la disponibilité du système Lync Server 2013.

  - **Assurez-vous que toutes les sauvegardes de données sont chiffrées et correctement gérées**   , supprimées, ou les médias de sauvegarde déplacés peuvent constituer une menace significative de la sécurité des données pour les déploiements de Lync Server 2013

Sur tout serveur Lync Server 2013, à l’exception de Standard Edition Server, l’instance SQL Server Express (instance RTCLOCAL) n’est pas accessible à distance et aucune exception de pare-feu local n’est créée, à l’exception de SQL Server Express sur un serveur Standard Edition Server. Sur un serveur Standard Edition Server, la base de données principale et la Banque centrale de gestion (CMS) sont configurées pour être accessibles à distance. Pour renforcer les bases de données SQL Server, vous pouvez procéder comme suit :

  - Personnalisez le pare-feu SQL Server Express sur les serveurs Standard Edition afin de limiter l’étendue des serveurs qui peuvent accéder à distance à la base de données. Par défaut, toute adresse IP peut accéder à distance à la base de données.

  - Utilisez SQL Server Configuration Manager pour spécifier les protocoles, adresses IP et ports pour l’accès distant SQL Server :
    
      - Lync Server 2013 utilise le protocole TCP/IP. Il prend en charge le protocole IP version 4 (IPv4), mais pas le protocole IP version 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 peut fonctionner dans un réseau doté d’une pile IP double activée.

        
        </div>
    
      - Lync Server 2013 prend en charge plusieurs adresses IP (cartes d’adresses réseau multi-résidentes). Vous pouvez spécifier que SQL Server écoute uniquement les adresses IP spécifiques (adresse individuelle ou sous-réseau) et utiliser des protocoles spécifiques uniquement.
    
      - Lync Server 2013 prend en charge les ports SQL Server statiques et dynamiques.

  - Exécutez SQL Server sur un port statique (non défini par défaut) et n’exécutez pas le navigateur SQL Server (de sorte qu’il ne puisse pas signaler le port d’écoute au client). Pour cela, il est nécessaire de disposer d’une configuration personnalisée sur chaque client SQL Server, y compris sur les serveurs frontaux, le serveur de surveillance, le serveur d’archivage et les consoles d’administration (exécutant Lync Server Management Shell, le panneau de configuration de Lync Server ou le générateur de topologie), et tous les autres serveurs exécutant des bases de données serveur Lync).

<div>


> [!NOTE]  
> L’accès aux bases de données doit être limité aux administrateurs de base de données approuvés. Un administrateur de base de données malveillant pouvait insérer ou modifier des données dans les bases de données pour obtenir des privilèges sur les serveurs Lync Server 2013 ou obtenir des informations sensibles de ces services, même si l’administrateur de la base de données n’a pas reçu d’accès direct ou contrôle des serveurs Lync Server 2013.



</div>

Pour plus d’informations sur les configurations personnalisées et le renforcement de bases de données SQL Server, voir l’article de blog NextHop intitulé « utilisation de Lync Server 2010 avec une configuration [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)réseau SQL Server personnalisée ».

<div>


> [!NOTE]  
> Vous pouvez également renforcer la protection des serveurs d’applications et des systèmes d’exploitation, mais vous pouvez utiliser une stratégie de groupe pour mettre en œuvre les verrouillages de sécurité dans le déploiement de Lync Server. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">renforcement et protection des serveurs et applications pour Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

