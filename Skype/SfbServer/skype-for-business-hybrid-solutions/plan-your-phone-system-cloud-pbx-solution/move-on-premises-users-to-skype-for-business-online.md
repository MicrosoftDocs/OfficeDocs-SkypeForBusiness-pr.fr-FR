---
title: Déplacer les utilisateurs locaux à Skype pour Business en ligne
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Résumé : Informations sur le déplacement local aux utilisateurs de Skype pour Business Online.'
ms.openlocfilehash: 1cb57e777b9353b1abb5b211563f5b6adc58e72c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882067"
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>Déplacer les utilisateurs locaux à Skype pour Business en ligne
 
**Résumé :** Informations sur le déplacement des utilisateurs locaux à Skype pour Business Online.
  
> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online. Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REPLACER L’UTILISATEUR DANS VOTRE ENVIRONNEMENT LOCAL.
Si la réinitialisation matérielle est effectuée avant l’installation du microprogramme minimal requis sur l’appareil, celui-ci utilise par défaut l’authentification par code confidentiel, ce qui n’est pas pris en charge par Skype Entreprise Online. Pour plus d’informations, reportez-vous à [L’obtention des téléphones de Skype pour Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Il s’agit d’une étape facultative qui est requise uniquement si vous déplacez des utilisateurs locaux vers Skype pour Business Online. Avant de commencer à déplacer les utilisateurs vers Skype pour Business Online, vérifiez que le Skype pour Business Connector en ligne (module Windows PowerShell) est déployée sur vos serveurs frontaux. Si elle n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Par ailleurs, pour préparer votre AD, vous devez configurer Azure AD Connect. La version d’AAD Connect que vous utilisez doit être de version 1.0.9125.0 ou version ultérieure. Si vous utilisez des outils d'une version antérieure d’AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement.
  
Déplacer les utilisateurs à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell dans votre déploiement sur site, mais vous devez disposer des informations d’identification d’administrateur pour votre déploiement d’Office 365.
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>Déplacement d’utilisateurs à l’aide de Skype pour Business le panneau de configuration

### <a name="to-move-a-user-to-skype-for-business-online"></a>Pour déplacer un utilisateur à Skype pour Business Online

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou csadministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne ayant Skype pour Business Server ou, au moins Skype pour les outils d’administration de serveur d’entreprise installés.
    
2. Dans le menu Démarrer ou d’un raccourci sur le bureau, ouvrez le Skype pour le panneau de configuration serveur Business.
    
    Vous pouvez également accéder le Skype pour le panneau de configuration serveur Business à l’aide de l’URL d’administration si vous avez configuré un.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Cliquez sur l’utilisateur, puis, dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers Skype Entreprise Online**.
    
6. Dans la page **Déplacer des utilisateurs vers Skype Entreprise Online**, lisez les informations, puis cliquez sur **Suivant**.
    
7. Dans la page suivante, si vous n’êtes pas encore connecté à Office 365, cliquez sur **se connecter à Office 365**, vos informations d’identification, cliquez sur **OK** , puis **suivant**.
    
8. Confirmez que le nombre d’utilisateurs à déplacer est correct, puis cliquez sur **Suivant**.
    
9. Dans la page suivante, vérifiez les résultats et cliquez sur **Fermer**.
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Déplacement d’utilisateurs à l’aide de Skype pour Business Server Management Shell

Pour déplacer un utilisateur local vers votre Skype pour client Business Online, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour votre client Microsoft Office 365. Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel s’exécute le service de Migration hébergé, dans le format suivant : _Https://\<nom complet du Pool\>/HostedMigration/ hostedmigrationService.svc_.
  
Vous pouvez déterminer l’URL du Service de Migration hébergé en affichant l’URL pour le Skype Business Online Centre d’administration pour le compte du client Office 365.
  
> [!NOTE]
> L’URL dépend des minuscules/majuscules. 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365

1. Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
2. Ouvrez le **Centre d’administration Skype Entreprise**.
    
3. Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant : 
    
     `https://admin0a.online.lync.com`
    
5. Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationService.svc**.
    
    L’URL qui en résulte, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

