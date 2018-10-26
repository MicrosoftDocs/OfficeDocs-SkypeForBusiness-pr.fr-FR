---
title: Migration des groupes Response Group
TOCTitle: Migration des groupes Response Group
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204931(v=OCS.15)
ms:contentKeyID: 49297322
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des groupes Response Group

 

_**Dernière rubrique modifiée :** 2012-10-19_

Une fois vos utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group comprend la copie des groupes d’agents, des files d’attente, des flux de travail et des fichiers audio, ainsi que le déplacement des objets contact Response Group du déploiement hérité vers le pool Lync Server 2013. Une fois la migration de vos groupes Response Group existants effectuée, les appels destinés aux groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.

> [!NOTE]  
> Même s’il est possible de migrer les groupes Response Group avant de placer tous les utilisateurs dans le pool Lync Server 2013, nous vous conseillons de déplacer d’abord les utilisateurs. En particulier, les utilisateurs qui sont des agents de groupe Response Group. En effet, pour pouvoir utiliser pleinement les nouvelles fonctionnalités, ces derniers doivent être placés dans le pool Lync Server 2013.

Avant de migrer les groupes Response Group, vous devez d’abord déployer un pool Lync Server 2013 qui comprenne l’application Response Group. L’application Response Group est installée et activée par défaut quand vous déployez Voix Entreprise. Pour vérifier que l’application Response Group est installée, exécutez l’applet de commande **Get-CsService–ApplicationServer**.

> [!NOTE]  
> Vous pouvez créer des groupes Response Group Lync Server 2013 dans le pool Lync Server 2013 avant de procéder à la migration de vos groupes Response Group hérités.

Pour effectuer la migration de groupes Response Group d’un pool hérité vers Lync Server 2013, il suffit d’exécuter l’applet de commande **Move-CsRgsConfiguration**. Avant d’exécuter **Move-CsRgsConfiguration**, vous devez installer le package des interfaces de compatibilité descendante Windows Management Instrumentation (WMI). Installez cette application en exécutant OCSWMIBC.msi. Vous trouverez OCSWMIBC.msi sur le média d’installation, dans le dossier d’installation.

> [!IMPORTANT]  
> L’applet de commande de migration de Response Group déplace la configuration de Response Group pour le pool entier. Vous ne pouvez sélectionner aucun groupe, file d’attente ou flux de travail spécifique à migrer.

Après avoir effectué la migration des groupes Response Group, vous devez mettre à jour l’URL que les agents formels utilisent pour se connecter et se déconnecter de leurs groupes Response Group. Par ailleurs, vous devez utiliser le Panneau de configuration Lync Server ou les applets de commande Lync Server Management Shell pour vous assurer que l’ensemble des groupes d’agents, files d’attente et flux de travail sont correctement déplacés.

> [!CAUTION]  
> Quand vous migrez des groupes Response Group, les groupes Response Group Office Communications Server 2007 R2 ne sont pas supprimés. Ne supprimez pas les groupes Response Group Office Communications Server 2007 R2. Si vous supprimez un groupe Response Group Office Communications Server 2007 R2, les groupes Response Group Lync Server 2013 cessent de fonctionner.

> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe Response Group Office Communications Server 2007 R2 est supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde afin de refaire fonctionner les groupes Response Group Lync Server 2013.

Quand vous exécutez l’applet de commande **Move-CsRgsConfiguration**, les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Cependant, si vous devez restaurer le pool hérité, vous devez exécuter l’applet de commande **Move-CsApplicationEndpoint**. Les objets contact seront ainsi replacés dans le pool hérité.

> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données du groupe Response Group du pool hérité tant que vous n’avez pas désaffecté le pool.

La procédure suivante de migration des configurations Response Group suppose que vous ayez une relation un à un entre vos pools hérités et les pools Lync Server 2013. Si vous planifiez de consolider ou de fractionner des pools pendant votre migration et votre déploiement, vous devez planifier le mappage d’un pool hérité à un pool Lync Server 2013.

## Pour effectuer la migration de configurations Response Group

1.  Recherchez OCSWMIBC.msi dans le dossier d’installation du support d’installation, puis installez-le.

2.  Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.

3.  Ouvrez Lync Server Management Shell.

4.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Exemple :
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si vous déployez l’onglet Response Group pour Microsoft Office Communicator 2007 R2 dans votre environnement Office Communications Server 2007 R2, supprimez l’onglet du fichier tabs.xml Office Communicator 2007 R2.
    
    > [!NOTE]  
    > Les agents formels ont utilisé l’onglet Response Group pour se connecter à leurs groupes de réponses avant de pouvoir recevoir des appels. Si vous déployez l’onglet Response Group, vous avez choisi l’emplacement du fichier tabs.xml Office Communicator 2007 R2 ce faisant.

6.  Fournissez aux utilisateurs l’URL mise à jour dont les agents ont besoin pour se connecter ou se déconnecter de leurs groupes de réponses.
    
    > [!NOTE]  
    > L’URL est généralement https://webpoolFQDN/RgsClients/Tab.aspx, où <em>webpoolFQDN</em> représente le nom de domaine complet du pool web associé au pool que vous venez de migrer vers Lync Server 2013.    
    > [!NOTE]  
    > Cette étape n’est pas exigée une fois que les utilisateurs ont effectué une mise à niveau vers Lync 2013, car l’URL est disponible à partir du menu <strong>Outils</strong> dans Lync.

## Pour vérifier la migration de groupes Response Group à l’aide du Panneau de configuration Lync Server

1.  Ouvrez Panneau de configuration Lync Server.

2.  Dans le volet de navigation gauche, cliquez sur **Services Response Group** .

3.  Sous l’onglet **Workflow**, vérifiez que tous les workflows de votre environnement Office Communications Server 2007 R2 sont répertoriés dans la liste.

4.  Cliquez sur l’onglet **File d’attente**, puis vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont répertoriées dans la liste.

5.  Cliquez sur l’onglet **Groupe**, puis vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont répertoriés dans la liste.

## Pour vérifier la migration de groupes Response Group à l’aide d’applets de commande

1.  Ouvrez Lync Server Management Shell.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
        Get-Help <cmdlet name> -Detailed

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsAgentGroup

3.  Vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

4.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsQueue

5.  Vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

6.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsWorkflow

7.  Vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

