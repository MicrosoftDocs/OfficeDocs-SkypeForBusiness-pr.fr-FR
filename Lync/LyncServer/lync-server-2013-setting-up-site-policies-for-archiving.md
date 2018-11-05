---
title: Configuration des stratégies de site pour l’archivage
TOCTitle: Configuration des stratégies de site pour l’archivage
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205325(v=OCS.15)
ms:contentKeyID: 49299040
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de site pour l’archivage

 

_**Dernière rubrique modifiée :** 2012-10-09_

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant et configurant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange mais que certains de vos utilisateurs sont hébergés sur Exchange 2013 et ont leurs boîtes aux lettres placées en archive permanente.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir la documentation de planification, de déploiement ou des opérations [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md).

> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive permanente d’Exchange contrôlent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Vous devez spécifier les options appropriées dans les configurations d’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Pour créer une stratégie d’archivage pour un site

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013.

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.
    
    Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir la documentation de planification, de déploiement ou des opérations [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md).

4.  Cliquez sur **Nouveau**, puis sur **Stratégie de site**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.

6.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez le nom pour la stratégie de site.
    
      - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
      - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.

7.  Cliquez sur **Valider**.

