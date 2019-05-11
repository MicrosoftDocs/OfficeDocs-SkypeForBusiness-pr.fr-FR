---
title: Affecter une stratégie de code confidentiel par utilisateur dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Résumé : Étape AV et OAuth certificats pour Skype pour Business Server.'
ms.openlocfilehash: 777944be2a2db32e4662b8afecac0023bdd2ab91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902666"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Affecter une stratégie de code confidentiel par utilisateur dans Skype pour Business Server

**Résumé :** Certificats étape AV et OAuth pour Skype pour Business Server.
  
La stratégie de code confidentiel (PIN) dans les conférences rendez-vous identification personnel est un des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le Skype pour le panneau de configuration serveur Business.
  
Le déploiement d’une ou plusieurs stratégies de code confidentiel par utilisateur est facultatif. Vous pouvez également déployer une stratégie de code confidentiel au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les droits et autorisations des utilisateurs concernant l’utilisation des codes confidentiels pour les conférences rendez-vous sont automatiquement définis sur ceux de la stratégie de code confidentiel globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.
  
Lorsque vous aurez créé au moins une stratégie de code confidentiel par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les contraintes que le serveur doit appliquer aux codes confidentiels créés et utilisés par un utilisateur particulier.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Pour attribuer une stratégie de code confidentiel par utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
   - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
   - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).
    
5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
   a. Cliquez sur **Ajouter un filtre**.
    
   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.
    
   c. Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).
    
   d. Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
    
    > [!TIP]
    > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**. 
  
   e. Cliquez sur **Rechercher**.
    
6. Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.
    
    > [!TIP]
    > Si vous voulez que la même stratégie de code confidentiel par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur **Actions**, puis sur **Attribuer des stratégies**. 
  
7. Dans **Attribuer des stratégies**, sous **Stratégie de code confidentiel**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]
    > Car il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue **Affecter les stratégies** , ** \<conserver comme est\> ** est activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.
  
   - Autoriser Skype pour Business Server à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
   - Cliquez sur le nom d’une stratégie de code confidentiel par utilisateur que vous avez définie dans la page **Stratégie de code confidentiel**.
    
     > [!TIP]
     > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur **Afficher** pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.
  
8. Lorsque vous avez terminé, cliquez sur **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie de code confidentiel par utilisateur à l’aide des applets de commande Windows PowerShell

Vous pouvez affecter des stratégies de code confidentiel par utilisateur à l’aide de Windows PowerShell et l’applet de commande **Grant-CsPinPolicy** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Pour affecter une stratégie de code confidentiel par utilisateur à un seul utilisateur

- La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondPinPolicy à l’utilisateur Ken Myer.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Pour affecter une stratégie de code confidentiel par utilisateur à plusieurs utilisateurs

- La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondUsersPinPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisée dans cette commande, voir [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Pour annuler l’affectation d’une stratégie de code confidentiel par utilisateur

- La commande suivante annule l’affectation d’une stratégie de code confidentiel par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Pour plus d’informations, voir [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Voir aussi

[Créer une nouvelle stratégie de code confidentiel dans Skype pour Business Server](create-a-new-pin-policy.md)
