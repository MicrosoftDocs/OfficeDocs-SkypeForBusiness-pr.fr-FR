---
title: Configuration de la stratégie globale pour l’archivage
TOCTitle: Configuration de la stratégie globale pour l’archivage
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204906(v=OCS.15)
ms:contentKeyID: 49297304
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la stratégie globale pour l’archivage

 

_**Dernière rubrique modifiée :** 2012-10-09_

Quand vous déployez vos serveurs frontaux, Lync Server crée une stratégie globale pour l’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. La stratégie globale vérifie si l’archivage est activé pour les communications internes et externes dans l’intégralité de votre déploiement, sauf si vous configurez des stratégies de site ou des stratégies utilisateur (lesquelles remplacent la stratégie globale), ou si vous utilisez l’intégration de Microsoft Exchange pour une partie ou l’ensemble de vos utilisateurs. Si vous utilisez l’intégration de Microsoft Exchange, la stratégie globale ne s’applique pas aux utilisateurs hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente.

Pour plus d’informations sur les stratégies d’archivage, notamment la hiérarchie des stratégies : globale, de site et utilisateur, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, des stratégies d’archive permanente Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Il est préférable de spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Pour configurer la stratégie globale pour l’archivage lors de l’utilisation de bases de données d’archivage Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes d’ouverture du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.

4.  Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
      - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.
    
      - Dans **Description**, fournissez des informations sur la stratégie (par exemple, stratégie globale de *nom\_division*).
    
      - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.

