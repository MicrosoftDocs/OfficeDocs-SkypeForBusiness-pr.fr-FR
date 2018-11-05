---
title: Déplacer les utilisateurs vers un autre outil dans Lync Server 2013
TOCTitle: Déplacer les utilisateurs vers un autre outil dans Lync Server 2013
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182600(v=OCS.15)
ms:contentKeyID: 49299210
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacer les utilisateurs vers un autre outil dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-11_

Vous pouvez utiliser Panneau de configuration Lync Server pour attribuer des utilisateurs à un serveur ou à un pool spécifique.

> [!TIP]  
> Le déplacement de tous les utilisateurs existants d’un pool source qui exécute Microsoft Office Communications Server 2007 R2 ou une version antérieure vers un pool de destination Lync Server 2013 dans un environnement Active Directory complexe peut ralentir la réplication Active Directory. Pour éviter ce problème, vous pouvez utiliser des filtres de recherche afin de déplacer séparément les utilisateurs à partir des pools qui exécutent Microsoft Office Communications Server 2007 R2 ou une version antérieure, ou utiliser Lync Server Management Shell pour déplacer des utilisateurs à l’aide de cmdlets. En outre, le filtrage fonctionne avec les utilisateurs Lync Server 2013.

## Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou pool

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.

6.  Dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers le pool**.

7.  Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.

8.  (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!WARNING]  
    > Si vous activez la case à cocher <strong>Forcer</strong>, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.

## Pour déplacer tous les utilisateurs d’un seul serveur ou pool vers un autre serveur ou pool

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.

5.  Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateurs que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.

6.  Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.

7.  (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!WARNING]  
    > Si vous activez la case à cocher <strong>Forcer</strong>, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.

## Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans **Recherche d’un utilisateur**, cliquez sur **Rechercher**, puis sur **Ajouter un filtre**.

5.  Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.

6.  Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.
    
    > [!NOTE]  
    > Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option <strong>Déplacer tous les utilisateurs vers le pool</strong> s’applique au sous-ensemble filtré des utilisateurs, et non à <strong><em>tous</em></strong> les utilisateurs possibles.

7.  Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.

8.  Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.

9.  (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!WARNING]  
    > Si vous activez la case à cocher <strong>Forcer</strong>, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur et les contacts). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés.

## Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide de Lync Management Shell

1.  Selon la manière dont vous exécutez les commandes Windows PowerShell (à savoir, localement ou à distance), vous avez besoin de vous connecter en tant que membre des rôles administratifs Lync Server 2013 appropriés comme suit :
    
    1.  Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous ouvrez une session directement sur un serveur frontal) : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et vous exécutez les commandes à distance sur un serveur frontal Standard Edition) : À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour déplacer des utilisateurs individuels, utilisez la cmdlet Move-CsUser comme suit :
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Où l’utilisateur à déplacer est Pilar Ackerman, lequel sera déplacé depuis le pool d’accueil qui lui est actuellement affecté vers le pool pool01.contoso.net

4.  Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec la cmdlet **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu à **Move-CsUser** :
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Les commandes combinées des cmdlets **Get-CsUser** et **Move-CsUser** peuvent donner le résultat suivant :
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

## Voir aussi

#### Autres ressources

[Modification des propriétés d’un compte d’utilisateur](lync-server-2013-modifying-user-account-properties.md)

