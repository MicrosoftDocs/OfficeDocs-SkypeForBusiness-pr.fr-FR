---
title: Configuration des options d’archivage pour un pool
TOCTitle: Configuration des options d’archivage pour un pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205200(v=OCS.15)
ms:contentKeyID: 49298620
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options d’archivage pour un pool

 

_**Dernière rubrique modifiée :** 2012-10-10_

Vous pouvez spécifier des options d’archivage à appliquer à des pools spécifiques en créant et en configurant des options dans une configuration de l’archivage pour chacun de ces pools. La configuration d’un pool remplace la configuration globale et la configuration d’un site, mais uniquement pour le pool spécifié dans la configuration du pool.

Pour plus d’informations sur les configurations d’archivage, notamment la hiérarchie des configurations (globale, de site et de pool), voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de la planification, la documentation du déploiement ou la documentation des opérations.

> [!NOTE]  
> Vous devez spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Pour configurer des options d’archivage au niveau du pool

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes d’ouverture du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.

5.  Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.

6.  Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :
    
      - **Désactiver l’archivage**
    
      - **Archiver les sessions de messagerie instantanée**
    
      - **Archiver les sessions de messagerie instantanée et de conférence web**

7.  Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :
    
      - Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Si vous souhaitez utiliser Microsoft Exchange Server pour le stockage des données d’archivage, activez la case à cocher **Intégration de Microsoft Exchange**.
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

8.  Cliquez sur **Valider**.

