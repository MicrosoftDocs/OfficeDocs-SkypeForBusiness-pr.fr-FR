---
title: "Créa. strat. arch. pr act/dés. arch. des comm. int/ext pr sites ou ut. part."
TOCtitle: "Créa. strat. arch. pr act/dés. arch. des comm. int/ext pr sites ou ut. part."
ms:assetid: 5864793a-ba72-470c-bb5b-9fb41e968896
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398385(v=OCS.15)
ms:contentKeyID: 49297246
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans Lync Server 2013, vous pouvez utiliser des stratégies pour activer ou désactiver l’archivage des communications internes et des communications externes pour les utilisateurs hébergés sur Lync Server 2013. Il s’agit notamment des stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut quand vous déployez Lync Server 2013.

  - Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.

Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le Panneau de configuration Lync Server 2013, accédez à la page **Stratégie d’archivage** dans le groupe **Archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau utilisateur. Si vous intégrez le stockage Lync Server avec le stockage Exchange 2013, les stratégies utilisateur d’Exchange sont prioritaires sur les stratégies d’archivage de Lync Server 2013.

Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de la planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, voir <a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</a> dans la documentation des opérations.<br />
Si vous avez activé l’intégration d’Microsoft Exchange pour votre déploiement, les stratégies d’Exchange déterminent l’activation de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.

## Pour créer une stratégie d’archivage pour un site ou des utilisateurs

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.

4.  Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie d’archivage au niveau du site, cliquez sur **Stratégie de site**, puis, dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée.
    
      - Pour créer une stratégie d’archivage au niveau de l’utilisateur, cliquez sur **Stratégie de l’utilisateur**.

5.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie (par exemple, externalContoso).
    
      - Dans **Description**, entrez des informations décrivant la stratégie (par exemple, stratégie d’archivage des utilisateurs externes pour Contoso).
    
      - Pour contrôler l’archivage des communications avec les utilisateurs internes, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications avec les utilisateurs externes, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.
    
    > [!IMPORTANT]  
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir <a href="lync-server-2013-applying-an-archiving-policy-to-users.md">Application d’une stratégie d’archivage à des utilisateurs</a>.

## Création d’une stratégie d’archivage à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également créer des stratégies d’archivage à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsArchivingPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Création d’une stratégie d’archivage au niveau de l’étendue Site

  - Cette commande crée une stratégie d’archivage pour le site Redmond :
    
        New-CsArchivingPolicy -Identity "site:Redmond"

## Création d’une stratégie d’archivage au niveau de l’étendue Utilisateur

  - Pour créer une stratégie d’archivage au niveau de l’étendue Utilisateur, il vous suffit de spécifier une identité unique lors de la création de la stratégie :
    
        New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"

## Création d’une stratégie d’archivage qui permet l’archivage des sessions de communications internes

  - Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés. Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une stratégie d’archivage qui permet d’archiver des sessions de messagerie instantanée internes, utilisez une commande similaire à ce qui suit :
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True

## Création d’une stratégie d’archivage qui permet l’archivage des sessions de communications internes et externes

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande permet de configurer la nouvelle stratégie visant à archiver les sessions de messagerie instantanée internes et externes :
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [New-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingPolicy).

## Voir aussi

#### Autres ressources

[Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

