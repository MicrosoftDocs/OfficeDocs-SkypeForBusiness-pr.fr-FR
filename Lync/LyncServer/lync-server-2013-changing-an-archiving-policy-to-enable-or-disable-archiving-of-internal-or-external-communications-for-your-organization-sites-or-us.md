---
title: "Mod. strat. arch. pr ac./dés. arch. des com. int./ext. pr vos org., sites, ut."
TOCtitle: "Mod. strat. arch. pr ac./dés. arch. des com. int./ext. pr vos org., sites, ut."
ms:assetid: b85dc3fb-8ebd-4e3c-ac90-fc79270ac867
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182576(v=OCS.15)
ms:contentKeyID: 49298646
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour votre organisation, vos sites ou vos utilisateurs

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans Lync Server 2013, vous pouvez utiliser des stratégies pour activer ou désactiver l’archivage des communications internes et des communications externes pour les utilisateurs hébergés sur Lync Server 2013. Il s’agit notamment des stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.

  - Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.

Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la page **Stratégie d’archivage** du groupe **Archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau utilisateur. Si vous intégrez le stockage Lync Server avec le stockage Exchange 2013, les stratégies utilisateur d’Exchange sont prioritaires sur les stratégies d’archivage de Lync Server 2013.

Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Si vous avez activé l’intégration d’Microsoft Exchange pour votre déploiement, les stratégies d’Exchange déterminent l’activation de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</a> dans la documentation des opérations.

## Pour modifier une stratégie d’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.

4.  Dans la liste des stratégies, effectuez l’une des opérations suivantes :
    
      - Pour modifier la stratégie pour l’ensemble de votre déploiement, cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour modifier la stratégie pour un seul site, cliquez sur le nom du site dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour modifier la stratégie pour un seul utilisateur ou groupe d’utilisateurs, cliquez sur l’utilisateur ou le groupe d’utilisateurs dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans la page **Modifier la stratégie d’archivage**, procédez comme suit :
    
      - Pour activer ou désactiver l’archivage interne de la stratégie, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour activer ou désactiver l’archivage externe de la stratégie, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.
    
    > [!IMPORTANT]  
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir <a href="lync-server-2013-applying-an-archiving-policy-to-users.md">Application d’une stratégie d’archivage à des utilisateurs</a>.

## Activation et désactivation de l’archivage à l’aide des applets de commande Lync Server PowerShell

L’archivage peut être activé et désactivé (à la fois pour les sessions de communication internes et externes) à l’aide de l’applet de commande **Set-CsArchivingPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Activation de l’archivage des sessions de communication internes

  - Pour activer l’archivage des sessions de communication internes, affectez la valeur True ($True) à la propriété **ArchiveInternal**. Par exemple :
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

## Activation de l’archivage des sessions de communication externes

  - Pour activer l’archivage des sessions de communication externes, affectez la valeur True ($True) à la propriété **ArchiveExternal**. Par exemple :
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

## Activation de l’archivage des sessions de communication internes et externes

  - Pour activer l’archivage des sessions de communication internes et des sessions de communication externes, affectez la valeur True aux deux propriétés **ArchiveInternal** et **ArchiveExternal** :
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

## Désactivation de l’archivage

  - Pour désactiver complètement l’archivage , affectez la valeur False ($False) aux deux propriétés **ArchiveInternal** et **ArchiveExternal**. Par exemple :
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingPolicy).

## Voir aussi

#### Autres ressources

[Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

