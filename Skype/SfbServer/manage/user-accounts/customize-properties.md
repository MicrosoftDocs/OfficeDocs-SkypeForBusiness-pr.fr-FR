---
title: Personnaliser les propriétés du compte d’utilisateur pour Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures décrites dans cette section pour modifier les propriétés du compte d’utilisateur individuel.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880867"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personnaliser les propriétés du compte d’utilisateur pour Skype pour Business Server
 
Vous pouvez utiliser les procédures décrites dans cette section pour modifier les propriétés du compte d’utilisateur individuel.
  
Il existe deux opérations de base qui peuvent être effectuées au niveau de chaque utilisateur :
  
- [Configurer les options de téléphonie pour un compte d’utilisateur spécifique](customize-properties.md#Tel_Op)
    
- [Déplacer les utilisateurs vers un autre pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurer les options de téléphonie pour un compte d’utilisateur spécifique
<a name="Tel_Op"> </a>

Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur a été activé pour Skype pour Business Server et l’organisation prend en charge la téléphonie).
  
Skype pour les options de téléphonie utilisateur Business Server sont les suivantes :
  
- **Audio/vidéo désactivé** L’utilisateur ne peut pas émettre des appels avec audio et vidéo.
    
- **PC à PC uniquement** L’utilisateur peut effectuer uniquement aux appels de PC à PC audio ou vidéo.
    
- **Voix entreprise** L’utilisateur peut utiliser le Skype pour infrastructure Business Server pour acheminer tous les appels entrants et sortants. L’utilisateur peut aussi passer des appels de PC à PC.
    
- **Contrôle d’appel distant** L’utilisateur peut utiliser Skype pour Business Server pour contrôler le téléphone de bureau et peut aussi passer des appels de PC à PC.
    
Pour plus d’informations sur la configuration de téléphonie dans une organisation, voir [Activer les utilisateurs pour Enterprise Voice dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) et le [Déploiement d’Enterprise Voice dans Skype pour Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) dans la documentation de déploiement.
  
1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou au trait identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher **.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.
    
6. Dans le menu **Edition** , cliquez sur **Modifier**.
    
7. En **téléphonie**, procédez comme suit :
    
   - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.
    
   - Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel ou un Enterprise Voice, cliquez sur **PC à PC uniquement**. Spécifiez une valeur pour **URI de ligne** pour le téléphone de l’utilisateur pour les communications audio de PC à PC.
    
   - Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de la Skype pour l’infrastructure d’entreprise, conformément à la classe de stratégie de service, y compris les communications audio de PC à PC, cliquez sur **Enterprise Voice**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Enterprise Voice. Dans **stratégie de plan de numérotation** et **la stratégie de voix**, spécifiez les stratégies appropriées pour l’utilisateur. Pour spécifier les règles de normalisation pour traduire les numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans la **stratégie d’emplacement**.
    
   - Pour permettre d’appel distant contrôle, qui permet aux utilisateurs de contrôler la ligne de leur téléphone de bureau à partir de Skype pour émettre des appels de PC à PC et PC à téléphone Business Server, cliquez sur **le contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit avoir une connexion à exchange (PBX) autocommutateur privé pour le routage des appels et le téléphone de bureau.
    
## <a name="move-users-to-another-pool"></a>Déplacer les utilisateurs vers un autre pool
<a name="Move_Users"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour affecter des utilisateurs à un serveur spécifique ou un pool.
  
> [!TIP]
> Déplacement de tous les utilisateurs existants à partir d’un pool source exécutant Lync Server 2010 ou version antérieure vers un Skype pour le pool de destination Business Server dans un environnement Active Directory complexe peut entraîner la réplication Active Directory plus lente. Pour éviter ce problème, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir des pools qui exécutent Lync Server 2010 ou précédemment séparément, ou vous pouvez utiliser Skype pour Business Server Management Shell pour déplacer des utilisateurs avec les applets de commande. En outre, la fonctionnalité de filtre fonctionne avec Skype pour les utilisateurs Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou un pool

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou au trait identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur **Rechercher **. 
    
5. Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste. 
    
6. Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.
    
7. Dans **Déplacer des utilisateurs**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs dans le **pool de serveurs d’inscriptions de Destination**.
    
8. (Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences). Si vous n’activez pas le, le compte et les données associées sont déplacées. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs d’un serveur ou pool vers un autre serveur ou un pool

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.
    
5. Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer dans un **pool de serveurs d’inscriptions Source**.
    
6. Dans le **pool de serveurs d’inscriptions de Destination**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs.
    
7. (Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences). Si vous n’activez pas le, le compte et les données associées sont déplacées. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la **Recherche d’un utilisateur**, cliquez sur **Rechercher**, puis cliquez sur **Ajouter un filtre**.
    
5. Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, sélectionnez **égal à**, sélectionnez **Actif nom complet du Pool**, puis cliquez sur **Rechercher**.
    
6. Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.
    
    > [!NOTE]
    > Lorsqu’un filtre est appliqué à un ensemble existant d’utilisateurs, l’option **déplacer tous les utilisateurs vers le pool** est dans le contexte du sous-ensemble d’utilisateurs, **tous les** utilisateurs possibles pas filtré.
  
7. Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer dans un **pool de serveurs d’inscriptions Source**.
    
8. Dans le **pool de serveurs d’inscriptions de Destination**, sélectionnez le pool dans lequel vous souhaitez déplacer les utilisateurs.
    
9. (Facultatif) Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, l’utilisateur a planifié des conférences et les contacts). Si vous n’activez pas le, le compte et les données associées sont déplacées. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Pour déplacer les utilisateurs d’un pool vers un autre à l’aide des applets de commande Windows Powershell

1. Selon si vous exécutez les commandes Windows PowerShell (c'est-à-dire, localement ou à distance), vous devez ouvrir une session en tant que membre de la Skype correcte des rôles d’administration Business Server comme suit :
    
   a. Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous connecter directement à un serveur frontal) : ouvrez une session sur l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou disposant des nécessaires droits d’utilisateur tels que décrits dans **Delegate Setup Permissions**.
    
   b. Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur Standard Edition serveur frontal) : à partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou le CsAdministrator Role, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Pour déplacer des utilisateurs individuels, utilisez l’applet de commande Move-CsUser comme suit :
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Où l’utilisateur à déplacer est l’utilisateur Pilar Ackerman et l’utilisateur sera déplacé à partir de leur pool d’accueil actuellement affecté vers le pool pool01.contoso.net
    
4. Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de commande **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu vers **Move-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Cela peuvent entraîner les commandes combinées des **Get-CsUser** et **Move-CsUser** :
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


