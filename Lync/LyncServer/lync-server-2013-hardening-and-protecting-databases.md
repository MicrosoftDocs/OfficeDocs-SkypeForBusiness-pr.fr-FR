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
ms.openlocfilehash: 6e1ef045253f6733ea3356baa6254a6c90926762
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Renforcement et protection des bases de données de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-05_

Microsoft Lync Server 2013 dépend également des bases de données SQL Server pour le stockage des informations utilisateur, de l’état de conférence, des données d’archivage et des enregistrements des détails des appels. Vous pouvez optimiser la disponibilité des données Lync Server 2013 sur les bases de données principales Lync Server en partitionnant les données d’application d’une manière qui améliore la tolérance de panne et simplifie la résolution des problèmes. Pour ce faire, partitionnez les données d’application comme suit :

  - **Les meilleures pratiques en matière**   de partitionnement de serveur séparent les fichiers de système d’exploitation, d’application et de programme de vos fichiers de données.

  - **Le stockage des fichiers journaux de transactions et des fichiers**   de base de données stocke ces fichiers séparément pour augmenter la tolérance de panne et optimiser la récupération, et les stocker sur un disque ou un volume chiffré.

  - **À l’aide**   du clustering de serveurs, mettez en cluster les serveurs principaux pour optimiser la disponibilité du système Lync Server 2013.

  - **S’assurer que toutes les sauvegardes de données sont chiffrées et correctement gérées**   les supports de sauvegarde perdus, ignorés ou égarés peuvent constituer une menace importante pour la sécurité des données pour les déploiements Lync Server 2013

Sur tout serveur Lync Server 2013 à l’exception du serveur Standard Edition, l’instance SQL Server Express (instance RTCLOCAL) n’est pas accessible à distance et aucune exception de pare-feu local n’est créée, à l’exception de SQL Server Express sur un serveur Standard Edition Server. Sur un serveur Standard Edition, la base de données principale et le magasin central de gestion sont configurés de sorte à être accessibles à distance. Pour renforcer la sécurisation des bases de données SQL Server, vous pouvez procéder comme suit :

  - Personnalisez le pare-feu SQL Server Express sur les serveurs Standard Edition, en limitant l’étendue des serveurs capables d’accéder à la base de données à distance. Par défaut, toute adresse IP peut accéder à la base de données à distance.

  - Utilisez le Gestionnaire de configuration SQL Server pour spécifier les protocoles, les adresses IP et les ports pour l’accès à distance à SQL Server :
    
      - Lync Server 2013 utilise le protocole TCP/IP. Il prend en charge le protocole IP version 4 (IPv4), mais pas le protocole IP version 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 peut fonctionner dans un réseau avec une pile IP double activée.

        
        </div>
    
      - Lync Server 2013 prend en charge plusieurs adresses IP (cartes d’adresses réseau multi-hébergées). Vous pouvez spécifier que SQL Server écoute uniquement des adresses IP particulières (adresse individuelle ou par sous-réseau) et utilise uniquement des protocoles spécifiques.
    
      - Lync Server 2013 prend en charge les ports SQL Server statiques et dynamiques.

  - Exécutez SQL Server sur un port statique (autre que le port par défaut) et n’exécutez pas SQL Server Browser (afin qu’il ne signale pas le port d’écoute au client). Cette opération nécessite une configuration personnalisée sur chaque client SQL Server, y compris les serveurs frontaux, le serveur de surveillance, le serveur d’archivage et les consoles d’administration (exécutant Lync Server Management Shell, le panneau de configuration Lync Server ou le générateur de topologies) et tous les autres serveurs exécutant des bases de données Lync Server).

<div>


> [!NOTE]  
> L’accès aux bases de données doit être limité aux administrateurs de bases de données approuvés. Un administrateur de base de données malveillant peut insérer ou modifier des données dans les bases de données pour acquérir des privilèges sur les serveurs Lync Server 2013 ou obtenir des informations sensibles auprès des services, même si l’administrateur de base de données n’a pas reçu d’accès direct ou contrôle des serveurs Lync Server 2013.



</div>

Pour plus d’informations sur les configurations personnalisées et sur le renforcement des bases de données SQL Server, voir l’article du blog NextHop, « utilisation de Lync Server 2010 avec une [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)configuration de réseau SQL Server personnalisée », à l’adresse.

<div>


> [!NOTE]  
> Vous pouvez également renforcer les systèmes d’exploitation et les serveurs d’applications, et vous pouvez utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité dans votre déploiement Lync Server. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">renforcement et protection des serveurs et des applications pour Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

