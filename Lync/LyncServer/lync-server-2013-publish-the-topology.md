---
title: 'Lync Server 2013 : publication de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e94e47536c8af6ef8fd3c22dba245b03c961c575
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512361"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Publier la topologie dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-01_

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les autorisations d’administrateur appropriées. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

Une fois que vous avez défini votre topologie dans le générateur de topologies, vous devez publier la topologie dans le magasin central de gestion. Le magasin central de gestion fournit un stockage robuste et schématisées des données nécessaires pour définir, configurer, maintenir, administrer, décrire et exploiter un déploiement Lync Server 2013. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées à ces données de configuration se produisent dans le magasin central de gestion, ce qui élimine les problèmes de « désynchronisation ». Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge.

<div>


> [!NOTE]  
> SQL Server a besoin d’un minimum de 20 Go d’espace disque disponible pour publier la topologie initiale et créer le serveur de gestion centralisée.



</div>

<div>


> [!NOTE]  
> Pour Enterprise Edition uniquement : pour pouvoir publier la topologie, le serveur principal SQL Server doit être en ligne et accessible, et les exceptions de pare-feu nécessaires doivent être configurées. Pour plus d’informations sur la spécification des exceptions de pare-feu, voir <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with Lync server 2013</A>. Pour plus d’informations sur la configuration de SQL Server, voir <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurer SQL Server pour Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Pour publier une topologie

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Sélectionnez le fichier de topologie sur l’ordinateur local. Si vous utilisez l’ordinateur sur lequel vous avez défini la topologie, il s’agit de l’emplacement où vous l’avez enregistré au cours d’une procédure précédente. Il s’agit en général du dossier Documents de l’utilisateur qui a configuré la topologie.

3.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **Créer des bases de données**, sélectionnez les bases de données à publier.
    
    <div>
    

    > [!NOTE]  
    > Si vous ne disposez pas des droits appropriés pour créer certaines bases de données, vous pouvez désactiver les cases à cocher en regard de celles-ci et demander à une personne dotée des droits appropriées de les créer plus tard. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.

    
    </div>

6.  Vous pouvez cliquer sur **Avancé**. Les options de placement de fichiers de données SQL Server avancées vous permettent de choisir parmi les options suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration des disques de votre serveur SQL Server et répartit les fichiers journaux et de données au meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**, puis sur **Suivant**.

7.  Sur la page **Sélectionner un serveur de gestion centralisée** , sélectionnez un pool frontal.

8.  Vous pouvez cliquer sur **Avancé**. Les options de placement de fichiers de données SQL Server avancées vous permettent de choisir entre les options suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration des disques de votre serveur SQL Server et répartit les fichiers journaux et de données au meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**.

9.  Cliquez sur **Suivant** pour terminer le processus de publication.

10. Au terme du processus, cliquez sur **Terminer**.
    
    Une fois la topologie publiée, vous pouvez commencer à installer un réplica local du magasin central de gestion sur chaque serveur exécutant Lync Server 2013 dans votre topologie. Nous vous recommandons de commencer par le premier pool frontal.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de serveurs frontaux et de pools frontaux pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

