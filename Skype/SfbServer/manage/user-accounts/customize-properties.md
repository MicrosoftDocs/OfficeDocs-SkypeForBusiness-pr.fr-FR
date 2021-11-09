---
title: Personnaliser les propriétés de compte d’utilisateur Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.
ms.openlocfilehash: c2a2f63e31d17e90cea528c3fc8ef88dd1952902
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856651"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personnaliser les propriétés de compte d’utilisateur Skype Entreprise Server
 
Les procédures dans cette section vous permettent de modifier les propriétés de chaque compte d’utilisateur.
  
Deux opérations de base peuvent être réalisées au niveau de l’utilisateur individuel :
  
- [Configurer les options de téléphonie pour un compte d’utilisateur spécifique](customize-properties.md#Tel_Op)
    
- [Déplacer des utilisateurs vers un autre pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurer les options de téléphonie pour un compte d’utilisateur spécifique
<a name="Tel_Op"> </a>

Vous pouvez personnaliser les paramètres téléphoniques d’un utilisateur spécifique (tant que l’utilisateur individuel a été activé pour la Skype Entreprise Server et que l’organisation prend en charge la téléphonie).
  
Skype Entreprise Server options de téléphonie utilisateur sont les suivantes :
  
- **Audio/vidéo désactivé** L’utilisateur ne peut pas effectuer d’appels avec l’audio et la vidéo.
    
- **PC à PC uniquement** L’utilisateur peut uniquement effectuer des appels audio ou vidéo de PC à PC.
    
- **Voix Entreprise** L’utilisateur peut utiliser l’infrastructure Skype Entreprise Server pour router tous les appels entrants et sortants. L’utilisateur peut aussi effectuer des appels de PC à PC.
    
- **Contrôle d’appel distant** L’utilisateur peut utiliser Skype Entreprise Server pour contrôler le téléphone de bureau et peut également effectuer des appels de PC à PC.
    
Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [Enable users for Voix Entreprise in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy Voix Entreprise in [Skype Entreprise Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.
  
1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.
    
6. Dans le menu **Edition**, cliquez sur **Modifier**.
    
7. Dans **Téléphonie**, procédez comme suit :
    
   - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.
    
   - Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou Voix Entreprise, cliquez sur **De PC à PC uniquement**. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.
    
   - Pour router les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype Entreprise conformément à la classe de stratégie de service, y compris la communication audio de PC à PC, cliquez sur **Voix Entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise. Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur. Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.
    
   - Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau à partir de Skype Entreprise Server pour effectuer des appels de PC à PC et des appels de PC à téléphone, cliquez sur Contrôle d’appel **distant.** Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.
    
## <a name="move-users-to-another-pool"></a>Déplacer des utilisateurs vers un autre pool
<a name="Move_Users"> </a>

Vous pouvez utiliser Skype Entreprise Server de contrôle d’accès pour affecter des utilisateurs à un serveur ou pool spécifique.
  
> [!TIP]
> Le déplacement de tous les utilisateurs existants d’un pool source exécutant Lync Server 2010 ou une antérieure vers un pool de destination Skype Entreprise Server dans un environnement Active Directory complexe peut entraîner une réplication Active Directory plus lente. Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs de pools exécutant Lync Server 2010 ou une édition antérieure séparément, ou vous pouvez utiliser Skype Entreprise Server Management Shell pour déplacer des utilisateurs avec des cmdlets. En outre, la fonctionnalité de filtrage fonctionne avec Skype Entreprise Server utilisateurs. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou pool

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**. 
    
5. Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste. 
    
6. Dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers le pool**.
    
7. Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.
    
8. (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs d’un seul serveur ou pool vers un autre serveur ou pool

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.
    
5. Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateurs que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.
    
6. Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.
    
7. (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans **la recherche d’utilisateur,** cliquez **sur Rechercher,** puis sur **Ajouter un filtre.**
    
5. Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.
    
6. Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.
    
    > [!NOTE]
    > Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option **Déplacer tous les utilisateurs vers le pool** s’applique au sous-ensemble filtré des utilisateurs, et non à **tous** les utilisateurs possibles.
  
7. Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.
    
8. Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.
    
9. (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    > [!CAUTION]
    > Si vous activez la case à cocher **Forcer**, le compte d’utilisateur est déplacé, mais toutes les données associées sont supprimées (par exemple, les conférences planifiées par l’utilisateur et les contacts). Si vous n’activez pas cette case à cocher, le compte et les données associées sont déplacés. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Pour déplacer des utilisateurs d’un pool vers un autre à l’aide Windows cmdlets PowerShell

1. Selon la façon dont vous exécutez les commandes Windows PowerShell (c’est-à-dire, localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administration Skype Entreprise Server corrects comme suit :
    
   a. Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous vous connectez directement à un serveur frontal) : connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
    
   b. Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous vous connectez à votre ordinateur et exécutez les commandes à distance sur un serveur frontal Édition Standard) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise,** puis sur Skype Entreprise Server **Management Shell.**
    
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


