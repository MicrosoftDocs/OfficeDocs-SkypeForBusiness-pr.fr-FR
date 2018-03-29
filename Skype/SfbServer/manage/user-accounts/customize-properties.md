---
title: Personnaliser les propriétés du compte d’utilisateur de Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Vous pouvez utiliser les procédures dans cette section pour modifier les propriétés de compte d’utilisateur individuel.
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a>Personnaliser les propriétés du compte d’utilisateur de Skype pour Business Server 2015
 
Vous pouvez utiliser les procédures dans cette section pour modifier les propriétés de compte d’utilisateur individuel.
  
Il existe deux opérations de base qui peuvent être effectuées au niveau de l’utilisateur individuel :
  
- [Configurer les options de téléphonie pour un compte d’utilisateur spécifique](customize-properties.md#Tel_Op)
    
- [Déplacer des utilisateurs vers un autre pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurer les options de téléphonie pour un compte d’utilisateur spécifique
<a name="Tel_Op"> </a>

Vous pouvez personnaliser les paramètres de téléphonie pour un utilisateur spécifique (tant que l’utilisateur a été activé pour Skype pour Business Server 2015 et l’organisation prend en charge la téléphonie).
  
Skype pour des options de téléphonie utilisateur Business Server sont les suivants :
  
- **Audio/vidéo désactivée** L’utilisateur ne peut pas effectuer des appels avec audio et vidéo.
    
- **PC à PC uniquement** L’utilisateur peut effectuer uniquement aux appels de PC à PC audio ou vidéo.
    
- **Voix Entreprise** L’utilisateur peut utiliser le Skype pour l’infrastructure de Business Server 2015 pour acheminer tous les appels entrants et sortants. L’utilisateur peut également effectuer des appels de PC à PC.
    
- **Contrôle d’appel distant** L’utilisateur peut utiliser le Skype pour Business Server 2015 pour contrôler le téléphone de bureau et peut aussi effectuer des appels de PC à PC.
    
Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [Déploiement de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) et de [permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) dans la documentation de déploiement.
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur recherche de **de ligne **.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.
    
6. Dans le menu **Edition** , cliquez sur **Modifier**.
    
7. En **téléphonie**, effectuez les opérations suivantes :
    
   - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivée**.
    
   - Pour activer les communications audio de PC à PC de l’utilisateur, mais le contrôle d’appel distant pas ou la Voix Entreprise, cliquez sur **PC à PC uniquement**. Spécifiez une valeur pour **l’URI de la ligne** pour le téléphone de l’utilisateur pour les communications audio de PC à PC.
    
   - Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de la Skype pour l’infrastructure d’entreprise selon la classe de stratégie de service, y compris la communication audio de PC à PC, cliquez sur **Voix Entreprise**. Dans l' **URI de la ligne**, spécifiez le numéro de téléphone de Voix Entreprise. Dans **stratégie de plan d’accès à distance** et **stratégie Voice**, spécifiez les stratégies appropriées pour l’utilisateur. Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans la **stratégie de l’emplacement**.
    
   - Pour activer l’appel distant contrôle, ce qui permet aux utilisateurs de contrôler leur ligne de téléphone de bureau à partir de Skype pour 2015 de serveur d’entreprise effectuer des appels de PC à PC et PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans l' **URI de la ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit avoir une connexion à exchange (PBX) privé de branche pour le routage d’appel et le téléphone de bureau.
    
## <a name="move-users-to-another-pool"></a>Déplacer des utilisateurs vers un autre pool
<a name="Move_Users"> </a>

Vous pouvez utiliser Skype pour Business Server du Panneau de configuration pour affecter des utilisateurs à un serveur spécifique ou d’un pool.
  
> [!TIP]
> Déplacement de tous les utilisateurs existants à partir d’un pool de source Lync Server 2010 est en cours d’exécution ou version antérieure vers un Skype pour le pool de destination 2015 de serveur d’entreprise dans un environnement Active Directory complexe peut entraîner la réplication Active Directory plus lente. Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir de pools de Lync Server 2010 sont en cours d’exécution ou précédemment séparément, ou vous pouvez utiliser Skype pour Business Server Management Shell pour déplacer des utilisateurs avec les applets de commande. En outre, la fonctionnalité de filtre fonctionne avec Skype pour les utilisateurs de Business Server 2015. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou un pool

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, dernier nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez, puis cliquez sur recherche de **de ligne **. 
    
5. Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste. 
    
6. Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés au pool**.
    
7. **Déplacer des utilisateurs**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs dans le **pool de Destination registrar**.
    
8. (Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié). Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs à partir d’un serveur ou un pool à un autre serveur ou un pool

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs au pool**.
    
5. **Déplacer des utilisateurs**, sélectionnez le pool qui contient les comptes d’utilisateur que vous souhaitez déplacer dans le **pool de registrar de Source**.
    
6. **Pool de registrar de Destination**, sélectionnez le pool que vous souhaitez déplacer les utilisateurs.
    
7. (Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié). Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs à partir d’un pool à un autre pool à l’aide d’un filtre

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la **Recherche de l’utilisateur**, cliquez sur **Rechercher**, puis cliquez sur **Ajouter un filtre**.
    
5. Dans les critères de recherche, sélectionnez **Pool de Registrar**sélectionnez **égal à**, sélectionnez le **FQDN de Pool en cours**et puis cliquez sur **Rechercher**.
    
6. Dans le menu **Action** , cliquez sur **déplacer tous les utilisateurs au pool**.
    
    > [!NOTE]
    > Lorsqu’un filtre est appliqué à un jeu existant d’utilisateurs, l’option **déplacer tous les utilisateurs au pool** est dans le contexte du sous-ensemble filtré des utilisateurs, pas **tous les** utilisateurs.
  
7. **Déplacer des utilisateurs**, sélectionnez le pool qui contient les comptes d’utilisateur que vous souhaitez déplacer dans le **pool de registrar de Source**.
    
8. **Pool de registrar de Destination**, sélectionnez le pool dans lequel vous souhaitez déplacer les utilisateurs.
    
9. (Facultatif) Si le pool ou le serveur de destination n’est pas disponible, activez la case à cocher **forcer** .
    
    > [!CAUTION]
    > Si vous sélectionnez **Force**, le compte d’utilisateur est déplacé, mais toutes les données utilisateur associé sont supprimées (par exemple, les conférences que l’utilisateur a planifié et contacts). Si vous ne le sélectionnez pas, le compte et les données associées sont déplacées. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Déplacer des utilisateurs à partir d’un pool à un autre à l’aide des applets de commande Windows Powershell

1. En fonction de la façon dont vous exécutez les commandes Windows PowerShell (c'est-à-dire, localement ou à distance), vous devez ouvrir une session en tant que membre de la Skype correct pour les rôles d’administration de Business Server 2015 comme suit :
    
   a. Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous connecter directement à un serveur frontal) : ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou disposant des nécessaires droits d’utilisateur comme décrit dans **Déléguer les autorisations de configuration**.
    
   b. Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécuter des commandes à distance sur un Standard Edition serveur frontal) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou le CsAdministrator rôle, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour déplacer des utilisateurs individuels, utilisez l’applet de commande Move-CsUser comme suit :
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Où correspond à l’utilisateur de déplacer l’utilisateur Pilar Ackerman et que l’utilisateur va de leur pool de domicile actuellement affectée à la pool01.contoso.net de pool
    
4. Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de commande **Get-CsUser** et passer de l’ensemble résultant des utilisateurs à **Move-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Cela peuvent entraîner les commandes combinées de **Get-CsUser** et **Move-CsUser** :
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


