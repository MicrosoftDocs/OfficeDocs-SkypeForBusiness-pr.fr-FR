---
title: 'Lync Server 2013 : renforcement et protection des bases de données'
TOCTitle: Renforcement et protection des bases de données de Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518330(v=OCS.15)
ms:contentKeyID: 60484455
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Renforcement et protection des bases de données de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 dépend également des bases de données SQL Server pour stocker les informations utilisateur, le statut de la conférence, les données d’archivage et les enregistrements des détails des appels. Vous pouvez augmenter la disponibilité des données Lync Server 2013 dans des bases de données d’arrière-plan Lync Server en partitionnant les données d’application de façon à améliorer la tolérance de panne et à simplifier l’identification et la résolution des problèmes. Pour parvenir à ces objectifs, partitionnez les données d’application de la façon suivante :

  - **Utilisez les meilleures pratiques en matière de partitionnement de serveur** : séparez les fichiers du système d’exploitation, des applications et des programmes de vos fichiers de données.

  - **Conservez les fichiers journaux des transactions et les fichiers de base de données** : stockez ces fichiers séparément pour augmenter la tolérance de panne et optimiser la restauration, et stockez-les sur un disque ou un volume chiffré.

  - **Utilisez la mise en cluster des serveurs** : regroupez les serveurs d’arrière-plan en cluster pour optimiser la disponibilité du système Lync Server 2013.

  - **Assurez-vous que toutes les sauvegardes de données sont chiffrées et gérées correctement** : des données perdues, supprimées ou placées au mauvais endroit peuvent exposer les déploiements de Lync Server 2013 à une menace significative concernant la sécurité des données.

Sur les serveurs Lync Server 2013, à l’exception du serveur Standard Edition, l’instance de SQL Server Express (instance RTCLOCAL) n’est pas accessible à distance et aucune exception de pare-feu local n’est créée, sauf pour SQL Server Express sur un serveur Standard Edition. Sur un serveur Standard Edition, la base de données d’arrière-plan et le magasin de gestion centralisée sont configurés de manière à être accessibles à distance. Pour renforcer les bases de données SQL Server, vous pouvez effectuer les opérations suivantes :

  - Personnalisez le pare-feu SQL Server Express sur les serveurs Standard Edition, en limitant l’étendue des serveurs en mesure d’accéder à distance à la base de données. Par défaut, une adresse IP peut accéder à distance à la base de données.

  - Utilisez SQL Server Configuration Manager pour spécifier les protocoles, les adresses IP et les ports pour l’accès à distance à SQL Server :
    
      - Lync Server 2013 utilise le protocole TCP/IP. Il prend en charge le protocole IP version 4 (IPv4), mais pas le protocole IP version 6 (IPv6).
        
        > [!NOTE]  
        > Lync Server 2013 peut fonctionner dans un réseau avec la double pile IP activée.    
      - Lync Server 2013 prend en charge plusieurs adresses IP (cartes d’adresse réseau multi-hébergées). Vous pouvez spécifier que SQL Server écoute uniquement des adresses IP spécifiques (adresse individuelle ou par masque de sous-réseau) et n’utilise que des protocoles spécifiques.
    
      - Lync Server 2013 prend en charge les ports SQL Server statiques et dynamiques.

  - Exécutez SQL Server sur un port statique (différent de la valeur par défaut) et n’exécutez pas SQL Server Browser (afin qu’il ne puisse pas signaler le port d’écoute au client). Cela implique une configuration personnalisée sur chaque client SQL Server, dont les serveurs frontaux, le serveur d’archivage et les consoles d’administration (en exécutant le shell de gestion Lync Server, le panneau de configuration de Lync Server ou le Générateur de topologie), ainsi que tous les autres serveurs exécutant des bases de données Lync Server).

> [!NOTE]  
> L’accès aux bases de données doit être réservé aux administrateurs de base de données approuvés. Un administrateur de base de données malveillant peur insérer ou modifier des données dans des bases de données afin de se procurer des droits sur des serveurs Lync Server 2013 ou des informations sensibles à partir des services, même si l’administrateur de base de données ne lui a pas accordé un accès direct ou le contrôle des serveurs Lync Server 2013.

Pour plus d’informations sur les configurations personnalisées et le renforcement des bases de données SQL Server, reportez-vous à l’article du blogue NextHop, « Using Lync Server 2010 with a Custom SQL Server Network Configuration » (Utilisation de Lync Server 2010 avec une configuration réseau SQL Server personnalisée) sous [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).

> [!NOTE]  
> Vous pouvez renforcer les systèmes d’exploitation et les serveurs d’applications et utiliser une stratégie de groupe pour mettre en œuvre des verrous de sécurité dans votre déploiement Lync Server. Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Renforcement et protection des serveurs et des applications pour Lync Server 2013</a>.
