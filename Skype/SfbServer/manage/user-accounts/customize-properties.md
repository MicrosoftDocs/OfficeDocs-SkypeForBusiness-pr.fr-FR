---
title: Personnaliser les propriétés de compte d’utilisateur Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mathavale
author: v-mathavale
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.
ms.openlocfilehash: f80847b57122539654541a444f427f4031ee6197
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314202"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personnaliser les propriétés de compte d’utilisateur Skype Entreprise Server
 
Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.
 
Deux opérations de base peuvent être réalisées au niveau de l’utilisateur individuel :
 
- [Configurer les options de téléphonie pour un compte d’utilisateur spécifique](#configure-telephony-options-for-a-specific-user-account)

- [Déplacer des utilisateurs vers un autre pool](#move-users-to-another-pool)
 
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurer les options de téléphonie pour un compte d’utilisateur spécifique

Vous pouvez personnaliser les paramètres téléphoniques d’un utilisateur spécifique (tant que l’utilisateur individuel a été activé pour la Skype Entreprise Server et que l’organisation prend en charge la téléphonie).
 
Skype Entreprise Server options de téléphonie utilisateur sont les suivantes :
 
|Options de téléphonie  |Description  |
|---------|---------|
|**Audio/vidéo désactivé**|L’utilisateur ne peut pas passer d’appels avec de l’audio et de la vidéo.|
|**De PC à PC uniquement** | L’utilisateur peut seulement passer des appels audio ou vidéo de PC à PC.|
|**Voix Entreprise** | L’utilisateur peut utiliser l’infrastructure Skype Entreprise Server pour router tous les appels entrants et sortants. L’utilisateur peut aussi effectuer des appels de PC à PC.|
|**Contrôle d’appel distant**   | L’utilisateur peut utiliser Skype Entreprise Server pour contrôler le téléphone de bureau et peut également effectuer des appels de PC à PC.|
 
Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [Enable users for Voix Entreprise in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy Voix Entreprise in [Skype Entreprise Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.
 
### <a name="configure-telephony-options-for-specific-users-using-new-control-panel"></a>Configurer les options de téléphonie pour des utilisateurs spécifiques à l’aide du nouveau Panneau de configuration 
 
1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.
 
3. Dans le volet gauche, sélectionnez **Utilisateurs.**
 
4. Dans la **zone de** recherche, tapez la première ou la première partie du nom complet, puis cliquez sur **Rechercher.**
 
5. Dans le tableau, double-cliquez sur le compte d’utilisateur à modifier.
 
6. Dans le panneau qui s’affiche, cliquez sur l’icône de crayon en face des **stratégies affectées.**
 
7. Dans **Téléphonie**, procédez comme suit :
 
    1. Pour désactiver les appels audio et vidéo pour l’utilisateur, sélectionnez **Audio/Vidéo** désactivé dans la liste liste.
 
    2. Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou le Voix Entreprise, sélectionnez PC à **PC** uniquement dans la liste de listes. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.
 
    3. Pour router les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype Entreprise conformément à la classe de stratégie de service, y compris la communication audio de PC à PC, sélectionnez **Voix Entreprise** dans la liste liste. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise. Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur. Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone composés par  l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans la liste de listes de listes listes des stratégies d’emplacement.
 
    4. Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau  à partir de Skype Entreprise Server pour passer des appels de PC à PC et des appels de PC à téléphone, sélectionnez Contrôle d’appel distant dans la liste de listes. Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="configure-telephony-options-for-specific-users-using-legacy-control-panel"></a>Configurer les options de téléphonie pour des utilisateurs spécifiques à l’aide du Panneau de configuration hérité
 
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
 
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
 
3. Dans le volet gauche, sélectionnez **Utilisateurs.**
 
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.
 
5. Dans le tableau, sélectionnez le compte d’utilisateur à modifier.
 
6. Dans le menu **Edition**, sélectionnez **Modifier**.
 
7. Dans **Téléphonie**, procédez comme suit :
 
    1. Pour désactiver les appels audio et vidéo pour l’utilisateur, sélectionnez **Audio/vidéo désactivé.**
 
    2. Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant Voix Entreprise, sélectionnez **PC à PC uniquement.** Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.
 
    3. Pour router les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype Entreprise conformément à la classe de stratégie de service, y compris la communication audio de PC à PC, sélectionnez **Voix Entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise. Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur. Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.
 
    4. Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau à partir de Skype Entreprise Server pour effectuer des appels de PC à PC et des appels de PC à téléphone, sélectionnez Contrôle d’appel **distant.** Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.

## <a name="move-users-to-another-pool"></a>Déplacer des utilisateurs vers un autre pool

Vous pouvez utiliser Skype Entreprise Server de contrôle d’accès pour affecter des utilisateurs à un serveur ou pool spécifique.
 
> [!TIP]
> Le déplacement de tous les utilisateurs existants d’un pool source exécutant Lync Server 2010 ou une antérieure vers un pool de destination Skype Entreprise Server dans un environnement Active Directory complexe peut entraîner une réplication Active Directory plus lente. Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir de pools qui exécutent Lync Server 2010 ou une antérieure séparément, ou vous pouvez utiliser Skype Entreprise Server Management Shell pour déplacer des utilisateurs avec des cmdlets. En outre, la fonctionnalité de filtre fonctionne avec Skype Entreprise Server utilisateurs. 
 
### <a name="move-selected-users-to-a-different-server-or-pool-using-new-control-panel"></a>Déplacer des utilisateurs sélectionnés vers un autre serveur ou pool à l’aide du nouveau Panneau de contrôle

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator. 
 
3. Dans le volet gauche, sélectionnez **Utilisateurs.**
 
4. Dans la **zone de** recherche, tapez la première ou la première partie du nom complet, puis cliquez sur **Rechercher.**
 
5. Dans le tableau, double-cliquez pour sélectionner un ou plusieurs utilisateurs spécifiques dans la liste. 

6. Dans le panneau qui s’affiche, cliquez sur l’icône de crayon en face du **pool de bureaux d’inscriptions.**
 
7. Dans **Déplacer des utilisateurs,** sélectionnez le pool vers qui vous souhaitez déplacer les utilisateurs dans la liste liste.
 
8. (Facultatif) Si le serveur ou le pool de destination n’est pas disponible, activez la **case à** cocher Forcer.
 
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="move-selected-users-to-a-different-server-or-pool-using-legacy-control-panel"></a>Déplacer des utilisateurs sélectionnés vers un autre serveur ou pool à l’aide du Panneau de contrôle hérité

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
 
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
 
3. Dans le volet gauche, sélectionnez **Utilisateurs.**
 
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**. 
 
5. Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste. 
 
6. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
 
7. Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.
 
8. (Facultatif) Si le serveur ou le pool de destination n’est pas disponible, activez la **case à** cocher Forcer.
 
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 
 
### <a name="move-users-from-one-pool-to-a-different-pool-by-using-a-filter-using-legacy-control-panel"></a>Déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre à l’aide du Panneau de contrôle hérité 

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
 
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
 
3. Dans le volet gauche, sélectionnez **Utilisateurs.**
 
4. Dans **la recherche d’utilisateur,** **sélectionnez Rechercher,** puis cliquez **sur Ajouter un filtre.**
 
5. Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.
 
6. Dans le menu **Action,** **sélectionnez Déplacer tous les utilisateurs vers le pool.**
 
    > [!NOTE]
    > Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option **Déplacer tous les utilisateurs vers le pool** s’applique au sous-ensemble filtré des utilisateurs, et non à **tous** les utilisateurs possibles.
 
7. Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.
 
8. Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.
 
9. (Facultatif) Si le serveur ou le pool de destination n’est pas disponible, activez la **case à** cocher Forcer.
 
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur et les contacts). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 
 
### <a name="move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Déplacer des utilisateurs d’un pool vers un autre à l’aide Windows PowerShell cmdlets

1. Selon la façon dont vous exécutez les commandes Windows PowerShell (c’est-à-dire, localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administration Skype Entreprise Server corrects comme suit :
 
    1. Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous vous connectez directement à un serveur frontal) : connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
 
    2. Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous vous connectez à votre ordinateur et exécutez les commandes à distance sur un serveur frontal Édition Standard) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
 
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise,** puis sur Skype Entreprise Server **Management Shell.**
 
3. Pour déplacer des utilisateurs individuels, utilisez la cmdlet Move-CsUser comme suit :
 
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Où l’utilisateur à déplacer est Pilar Ackerman, lequel sera déplacé depuis le pool d’accueil qui lui est actuellement affecté vers le pool pool01.contoso.net
 
4. Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec la cmdlet **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu à **Move-CsUser** :
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Les commandes associées de **Get-CsUser** et de **Move-CsUser** peuvent aboutir au résultat suivant :
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


