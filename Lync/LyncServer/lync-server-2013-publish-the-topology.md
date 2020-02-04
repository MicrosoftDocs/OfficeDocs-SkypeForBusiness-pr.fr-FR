---
title: 'Lync Server 2013 : Publication de la topologie'
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
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Publication de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-01_

Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les autorisations et les droits d’administrateur appropriés. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

Après avoir défini votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central. Le centre de gestion central fournit un stockage fiable schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement Lync Server 2013. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion, ce qui élimine les problèmes de synchronisation. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie, y compris les serveurs de périphérie.

<div>


> [!NOTE]  
> SQL Server a besoin d’un minimum de 20 Go d’espace disque libre pour la publication de la topologie initiale et la création du serveur de gestion central.



</div>

<div>


> [!NOTE]  
> Pour Enterprise Edition uniquement : pour publier la topologie, le serveur principal SQL Server doit être connecté et accessible avec des exceptions de pare-feu. Pour plus d’informations sur la spécification des exceptions de pare-feu, voir <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Présentation de la configuration requise pour le pare-feu pour SQL Server avec Lync Server 2013</A>. Pour plus d’informations sur la configuration de SQL Server, voir <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurer SQL Server pour Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Pour publier une topologie

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Sélectionnez cette option pour ouvrir la topologie à partir d’un fichier local. Si vous utilisez l’ordinateur sur lequel vous avez défini la topologie, il se trouve à l’emplacement où vous l’avez enregistrée aux étapes précédentes. En règle générale, il s’agit du dossier Documents de l’utilisateur qui a configuré la topologie.

3.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez publier.
    
    <div>
    

    > [!NOTE]  
    > Si vous ne disposez pas des droits appropriés pour créer les bases de données, vous pouvez désactiver les cases à cocher en regard de celles-ci et demander à une personne dotée des droits appropriées de les créer plus tard. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync Server 2013</A>.

    
    </div>

6.  Vous pouvez cliquer sur **Avancé**. Les options de placement des fichiers de données avancées SQL Server vous permettent de sélectionner les options suivantes :
    
      - **Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**, puis sur **Suivant**.

7.  Dans la page **Sélectionner le serveur de gestion centrale** , sélectionnez un pool frontal.

8.  Vous pouvez cliquer sur **Avancé**. Les options de placement des fichiers de données avancées SQL Server vous permettent de sélectionner l’une des options suivantes :
    
      - **Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK**.

9.  Cliquez sur **Suivant** pour terminer le processus de publication.

10. Lorsque le processus de publication est terminé, cliquez sur **Terminer**.
    
    Lorsque la topologie a été correctement publiée, vous pouvez commencer à installer une réplique locale du magasin de gestion central sur chaque serveur exécutant Lync Server 2013 dans votre topologie. Il est recommandé de commencer par le premier pool frontal.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des serveurs et des pools frontaux pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

