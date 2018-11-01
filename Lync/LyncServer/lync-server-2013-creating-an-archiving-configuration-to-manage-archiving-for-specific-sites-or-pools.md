---
title: "Créa. d’une conf. d’arch. pour gérer l’arch. pour des sites ou pools part."
TOCtitle: "Créa. d’une conf. d’arch. pour gérer l’arch. pour des sites ou pools part."
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205251(v=OCS.15)
ms:contentKeyID: 49298773
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’une configuration d’archivage pour gérer l’archivage pour des sites ou des pools spécifiques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser les configurations de l’archivage pour contrôler la mise en œuvre de l’archivage dans votre déploiement. Ces configurations sont les suivantes :

  - Une configuration globale qui est créée par défaut si vous déployez Lync Server 2013.

  - Des configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour indiquer comment l’archivage est mis en œuvre pour certains sites ou pools.

Vous devez mettre en place les configurations d’archivage avant de déployer l’archivage même, mais vous pouvez les modifier, en ajouter et en supprimer après le déploiement. Pour plus d’informations sur la mise en œuvre de configurations d’archivage, y compris les options que vous pouvez indiquer et la hiérarchie de ces configurations, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans les documentations de planification, de déploiement ou des opérations.

> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer les stratégies d’archivage pour indiquer son activation pour les communications internes, pour les communications externes ou pour les deux concernant les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications, qu’elles soient internes ou externes. Avant l’activation de l’archivage dans une quelconque stratégie, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, au besoin, pour les sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.<br />
Après avoir déployé l’archivage, si vous décidez d’utiliser l’intégration à Microsoft Exchange pour stocker les données et les fichiers d’archivage sur des serveurs Exchange 2013 et si tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devriez supprimer la configuration de la base de données SQL Server de votre topologie. Pour ce faire, vous devez utiliser le Générateur de topologie. Pour plus d’informations, voir <a href="lync-server-2013-changing-archiving-database-options.md">Modification des options de la base de données d’archivage dans Lync Server 2013</a> dans la documentation des opérations.

## Pour créer une configuration d’archivage pour un site ou un pool

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une configuration d’archivage de site, cliquez sur **Configuration du site** et, dans **Sélectionner un site**, indiquez le site à configurer pour l’archivage.
    
      - Pour créer une configuration d’archivage de pool, cliquez sur **Configuration du pool** et, dans **Sélectionner un pool**, indiquez le pool à configurer pour l’archivage.

5.  Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
      - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Afin d’activer l’archivage aussi bien pour les sessions de messagerie instantanée que les conférences web, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
      - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

6.  Aussi, dans **Créer un paramètre d’archivage**, procédez comme suit :
    
      - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
      - Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cochez la case **Intégration Microsoft Exchange**.
    
      - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
        
          - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.

7.  Cliquez sur **Valider**.

## Création de paramètres de configuration d’archivage à l’aide des applets de commande Lync Server

Vous pouvez aussi créer des paramètres de configuration d’archivage à l’aide de Windows PowerShell et de l’applet de commande New-CsArchivingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Création d’une collection de paramètres de configuration d’archivage pour un site

  - La commande suivante crée une collection de paramètres de configuration d’archivage pour le site Redmond :
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

## Création d’une collection de paramètres de configuration d’archivage n’autorisant que l’archivage de messagerie instantanée

  - Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration d’archivage qui autorisent par défaut l’archivage des sessions de messagerie instantanée, utilisez une simple commande comme celle-ci :
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

## Indication de plusieurs valeurs de propriétés pendant la création de paramètres de configuration d’archivage

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et pour bloquer la messagerie du service d’archivage afin de le rendre non disponible :
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

Pour plus d’informations, voir la rubrique d’aide de l’applet de commande [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration).

## Voir aussi

#### Concepts

[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Autres ressources

[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

