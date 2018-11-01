---
title: Migration des groupes Response Group
TOCTitle: Migration des groupes Response Group
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204854(v=OCS.15)
ms:contentKeyID: 49297038
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des groupes Response Group

 

_**Dernière rubrique modifiée :** 2013-09-23_

Une fois vos utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group comprend la copie des groupes d’agents, des files d’attente, des flux de travail et des fichiers audio, ainsi que le déplacement des objets contact Response Group du déploiement hérité vers le pool Lync Server 2013. Une fois la migration de vos groupes Response Group existants effectuée, les appels destinés aux groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.

> [!NOTE]  
> Même s’il est possible de migrer les groupes Response Group avant de placer tous les utilisateurs dans le pool Lync Server 2013, nous vous conseillons de déplacer d’abord les utilisateurs. En particulier, les utilisateurs qui sont des agents de groupe Response Group. En effet, pour pouvoir utiliser pleinement les nouvelles fonctionnalités, ces derniers doivent être placés dans le pool Lync Server 2013.

Avant de migrer les groupes Response Group, vous devez d’abord déployer un pool Lync Server 2013 qui comprenne l’application Response Group. L’application Response Group est installée et activée par défaut quand vous déployez Voix Entreprise. Pour vérifier que l’application Response Group est installée, exécutez l’applet de commande **Get-CsService –ApplicationServer**.

> [!NOTE]  
> Vous pouvez créer des groupes Response Group Lync Server 2013 dans le pool Lync Server 2013 avant de procéder à la migration de vos groupes Response Group hérités.

Pour effectuer la migration de groupes Response Group d’un pool hérité vers Lync Server 2013, il suffit d’exécuter l’applet de commande **Move-CsRgsConfiguration**.

> [!IMPORTANT]  
> L’applet de commande de migration de Response Group déplace la configuration de Response Group pour le pool entier. Vous ne pouvez sélectionner aucun groupe, file d’attente ou flux de travail spécifique à migrer.

Après avoir migré les groupes Response Group, utilisez les applets de commande du Panneau de configuration Lync Server ou de Lync Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès.

Quand vous migrez des groupes Response Group, les groupes Response Group Lync Server 2010 ne sont pas supprimés. Quand vous gérez des groupes Response Group après la migration en utilisant le Panneau de configuration Lync Server ou Lync Server Management Shell, vous pouvez voir les groupes Response Group Lync Server 2010 et Lync Server 2013. N’appliquez de mises à jour qu’aux groupes Response Group Lync Server 2013. Les groupes Response Group Lync Server 2010 sont conservés uniquement à des fins de restauration.

> [!CAUTION]  
> Une fois la migration terminée et les groupes Response Group créés, le panneau de configuration Lync Server et Lync Server Management Shell affichent les versions Lync Server 2010 et Lync Server 2013 de chaque groupe Response Group. N’utilisez pas Panneau de configuration Lync Server ou Lync Server Management Shell pour supprimer les groupes Response Group Lync Server 2010. Si vous en supprimez un, le groupe Response Group correspondant créé lors de la migration ne fonctionnera plus. Les groupes Response Group Lync Server 2010 seront supprimés lorsque vous désactivez le pool Lync Server 2010.

> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe Response Group Lync Server 2010 doit être supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde afin de refaire fonctionner les groupes Response Group Lync Server 2013.

Lync Server 2013 introduit une nouvelle fonctionnalité Response Group appelée **Type de flux de travail**. Le **Type de flux de travail** peut être **Géré** ou **Non géré**. Tous les groupes Response Group sont migrés avec le **Type de flux de travail** défini à **Non géré** et avec une liste de gestionnaires vide.

Quand vous exécutez l’applet de commande **Move-CsRgsConfiguration**, les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Cependant, si vous devez restaurer le pool hérité, vous devez exécuter l’applet de commande **Move-CsApplicationEndpoint**. Les objets contact seront ainsi replacés dans le pool hérité.

La procédure suivante de migration des configurations Response Group suppose que vous ayez une relation un à un entre vos pools hérités et les pools Lync Server 2013. Si vous planifiez de consolider ou de fractionner des pools pendant votre migration et votre déploiement, vous devez planifier le mappage d’un pool hérité à un pool Lync Server 2013.

## Pour effectuer la migration de configurations Response Group

1.  Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Exemple :
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Après avoir effectué la migration de groupes Response Group et d’agents vers le pool Lync Server 2013, l’URL que les agents utilisent pour se connecter et se déconnecter est une URL Lync Server 2013. Elle est disponible à partir du menu **Outils**. Rappelez aux agents de mettre à jour les références telles que les signets en utilisant la nouvelle URL.

## Pour vérifier la migration du groupe de réponses en utilisant Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation gauche, cliquez sur **Services Response Group**.

4.  Sous l’onglet **Flux de travail**, vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Cliquez sur l’onglet **File d’attente**, puis vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.

6.  Cliquez sur l’onglet **Groupe**, puis vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

## Pour vérifier la migration de groupes Response Group à l’aide de Lync Server Management Shell

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalReadOnlyAdmins ou qui soit au moins membre du rôle CsViewOnlyAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
        Get-Help <cmdlet name> -Detailed

3.  Exécutez :
    
        Get-CsRgsAgentGroup

4.  Vérifiez que tous les groupes d’agents de votre environnement Lync Server 2010 sont inclus dans la liste.

5.  Exécutez :
    
        Get-CsRgsQueue

6.  Vérifiez que toutes les files d’attente de votre environnement Lync Server 2010 sont incluses dans la liste.

7.  Exécutez :
    
        Get-CsRgsWorkflow

8.  Vérifiez que tous les flux de travail de votre environnement Lync Server 2010 sont inclus dans la liste.

