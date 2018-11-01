---
title: Configuration des options d’archivage au niveau global
TOCTitle: Configuration des options d’archivage au niveau global
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205233(v=OCS.15)
ms:contentKeyID: 49298708
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options d’archivage au niveau global

 

_**Dernière rubrique modifiée :** 2012-10-10_

Lorsque vous publiez votre topologie après avoir ajouté une fonctionnalité d’archivage, Lync Server crée une configuration globale de l’archivage. Par défaut, aucune option d’archivage n’est activée dans cette configuration globale. La configuration globale détermine quelles options sont activées au niveau de l’ensemble de votre déploiement. Cependant, si vous créez des configurations de site ou de pool, celles-ci sont prioritaires sur la configuration globale.

Pour plus d’informations sur les configurations d’archivage, notamment sur la hiérarchie des configurations de niveau global, site ou pool, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Vous devez spécifier toutes les options appropriées pour les configurations d’archivage avant d’activer la fonctionnalité d’archivage.

## Pour configurer les options d’archivage au niveau global

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :
    
      - **Désactiver l’archivage**
    
      - **Archiver les sessions de messagerie instantanée**
    
      - **Archiver les sessions de messagerie instantanée et de conférence web**

6.  Dans la page **Modifier le paramètre d’archivage - Global**, effectuez également les opérations suivantes :
    
      - Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server pour le stockage des données d’archivage, activez la case à cocher **Intégration de Microsoft Exchange**.
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

7.  Cliquez sur **Valider**.

