---
title: Configuration des options d’archivage d’un site
TOCTitle: Configuration des options d’archivage d’un site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204930(v=OCS.15)
ms:contentKeyID: 49297319
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options d’archivage d’un site

 

_**Dernière rubrique modifiée :** 2012-10-09_

Vous pouvez spécifier l’application d’options d’archivage à des sites spécifiques en créant et en configurant les options appropriées dans une configuration d’archivage pour chacun de ces sites. La configuration d’un site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration du site.

Pour plus d’informations sur les configurations d’archivage, notamment la hiérarchie des configurations (globale, de site et de pool), voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Il est préférable de spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.

> [!IMPORTANT]  
> Pour activer l’archivage, vous devez spécifier les stratégies d’archivage qui contrôlent l’archivage des communications internes et externes au niveau global et, si nécessaire, au niveau utilisateur et au niveau du site. Si vous configurez des stratégies de niveau utilisateur, vous devez également assigner les stratégies utilisateur à des utilisateurs spécifiques. Pour plus d’informations sur la création et la configuration de stratégies d’archivage, voir <a href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Gestion de l'archivage des communications internes et externes dans Lync Server 2013</a> dans la documentation des opérations.

## Pour configurer les options d’archivage au niveau du site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes d’ouverture du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.

5.  Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.

6.  Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
      - Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
      - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

7.  Dans **Créer un paramètre d’archivage**, procédez comme suit :
    
      - Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Si vous souhaitez utiliser Microsoft Exchange Server pour le stockage des données d’archivage, activez la case à cocher **Intégration de Microsoft Exchange**.
    
      - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

8.  Cliquez sur **Valider**.

