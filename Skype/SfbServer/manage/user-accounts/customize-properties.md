---
title: Personnaliser des propriétés de compte d’utilisateur pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures décrites dans cette section pour modifier des propriétés de compte d’utilisateur individuelles.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275072"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personnaliser des propriétés de compte d’utilisateur pour Skype entreprise Server
 
Vous pouvez utiliser les procédures décrites dans cette section pour modifier des propriétés de compte d’utilisateur individuelles.
  
Deux opérations de base peuvent être effectuées au niveau utilisateur individuel:
  
- [Configurer les options de téléphonie pour un compte d’utilisateur spécifique](customize-properties.md#Tel_Op)
    
- [Déplacer des utilisateurs vers un autre pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurer les options de téléphonie pour un compte d’utilisateur spécifique
<a name="Tel_Op"> </a>

Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur individuel a été activé pour Skype entreprise Server et l’Organisation prend en charge la téléphonie).
  
Les options de téléphonie de l’utilisateur Skype entreprise Server incluent les éléments suivants:
  
- **Audio/vidéo désactivé** L’utilisateur ne peut pas passer d’appels à l’aide de l’audio et de la vidéo.
    
- **PC à PC uniquement** L’utilisateur peut passer des appels audio ou vidéo de PC à PC.
    
- **Voix entreprise** L’utilisateur peut utiliser l’infrastructure du serveur Skype entreprise pour acheminer tous les appels entrants et sortants. L’utilisateur peut également passer des appels de PC à PC.
    
- **Contrôle d’appel distant** L’utilisateur peut utiliser Skype entreprise Server pour contrôler le téléphone de bureau et peut également passer des appels de PC à PC.
    
Pour plus d’informations sur la configuration de la téléphonie pour une organisation, reportez-vous à la rubrique [activer les utilisateurs d’Enterprise Voice dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) et [déployer Enterprise Voice dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) dans la documentation de déploiement.
  
1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher. **.
    
5. Dans la table, cliquez sur le compte d’utilisateur que vous voulez modifier.
    
6. Dans le menu **édition** , cliquez sur **modifier**.
    
7. En **téléphonie**, procédez comme suit:
    
   - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **audio/vidéo désactivé**.
    
   - Pour activer les communications audio de PC à ordinateur pour l’utilisateur, mais pas le contrôle d’appel distant ni la voix entreprise, cliquez sur **PC à PC uniquement**. Spécifiez une valeur pour **URI ligne** pour le téléphone utilisée par l’utilisateur pour les communications audio de PC à PC.
    
   - Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Skype entreprise conformément à la classe de la politique de service, y compris la communication audio de PC à PC, cliquez sur **voix entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone d’entreprise voix. Dans **politique de plan** de numérotation et de **stratégie vocale**, spécifiez les stratégies appropriées pour l’utilisateur. Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone numérotés par l’utilisateur au format E. 164, sélectionnez le profil d’emplacement approprié dans la **politique d’emplacement**.
    
   - Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau dans Skype entreprise Server afin de passer des appels de PC à PC et des appels de PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone du contrôle d’appel distant. Pour le routage des appels, l’utilisateur doit avoir un téléphone de bureau et une connexion PBX (Private Branch Exchange).
    
## <a name="move-users-to-another-pool"></a>Déplacer des utilisateurs vers un autre pool
<a name="Move_Users"> </a>

Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour attribuer des utilisateurs à un serveur ou un pool spécifique.
  
> [!TIP]
> Le déplacement de tous les utilisateurs existants à partir d’un pool de sources qui exécute Lync Server 2010 ou une version antérieure vers un pool de destination Skype entreprise Server dans un environnement Active Directory complexe peut ralentir la réplication Active Directory. Pour éviter ce problème, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs de pools exécutant Lync Server 2010 ou une version antérieure séparément, ou vous pouvez utiliser Skype entreprise Server Management Shell pour déplacer des utilisateurs avec des cmdlets. Par ailleurs, la fonctionnalité filtre fonctionne avec les utilisateurs de Skype entreprise Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer des utilisateurs sélectionnés vers un autre serveur ou pool

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher. **. 
    
5. Dans le tableau, sélectionnez un utilisateur ou des utilisateurs spécifiques dans la liste. 
    
6. Dans le menu **action** , cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.
    
7. Dans **déplacer les utilisateurs**, sélectionnez le groupe dans lequel vous souhaitez déplacer les utilisateurs dans le **pool d’inscriptions de destination**.
    
8. Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais les données utilisateur associées sont supprimées (par exemple, conférences que l’utilisateur a planifiées). Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs d’un serveur ou d’un pool vers un autre serveur ou pool

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.
    
5. Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.
    
6. Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le groupe auquel vous voulez déplacer les utilisateurs.
    
7. Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais les données utilisateur associées sont supprimées (par exemple, conférences que l’utilisateur a planifiées). Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs d’un groupe vers un autre à l’aide d’un filtre

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la **recherche d’utilisateur**, cliquez sur **Rechercher**, puis sur Ajouter un **filtre**.
    
5. Dans les critères de recherche, sélectionnez **pool de bureaux**d’enregistrement, sélectionnez **égal à**, sélectionnez **nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.
    
6. Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.
    
    > [!NOTE]
    > Lorsque vous appliquez un filtre à un ensemble d’utilisateurs existant, l’option **déplacer tous les utilisateurs vers le pool** est dans le contexte du sous-ensemble filtré d’utilisateurs, et non de **tous** les utilisateurs possibles.
  
7. Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.
    
8. Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le pool dans lequel vous voulez déplacer les utilisateurs.
    
9. Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez l’option **force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associées sont supprimées (par exemple, les conférences que l’utilisateur a planifiées et les contacts). Si vous ne la sélectionnez pas, le compte et les données associées sont déplacés. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Pour déplacer des utilisateurs d’un pool à un autre à l’aide des cmdlets Windows PowerShell

1. En fonction de la manière dont vous exécutez les commandes Windows PowerShell (c’est-à-dire, localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administrateur de Skype entreprise Server appropriés comme suit:
    
   a. Si vous exécutez les commandes sur l’ordinateur local (par exemple, si vous vous connectez directement à un serveur frontal): Connectez-vous à l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec la configuration nécessaire. droits d’utilisateur, tels que décrits dans **autorisations de configuration de délégué**.
    
   b. Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, si vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition): à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou à CsAdministrator pour vous connecter à n’importe quel ordinateur dans votre déploiement interne.
    
2. Démarrer Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Pour déplacer des utilisateurs uniques, utilisez l’applet de passe Move-CsUser en procédant comme suit:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Lorsque l’utilisateur se déplace, c’est l’utilisateur Pilar Arès, et l’utilisateur est déplacé de sa liste de ressources personnelles actuellement affectées au pool pool01.contoso.net
    
4. Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de passe **Get-Csuser** et transmettez le jeu d’utilisateurs obtenu à **Move-Csuser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Les commandes combinées de **Get-Csuser** et **Move-Csuser** peuvent être à l’origine:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


