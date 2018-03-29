---
title: Déplacer les utilisateurs locaux à Skype pour professionnels en ligne
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Résumé : Informations sur le déplacement sur site aux utilisateurs de Skype pour les entreprises en ligne.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>Déplacer les utilisateurs locaux à Skype pour professionnels en ligne
 
**Résumé :** Informations sur le déplacement des utilisateurs locaux à Skype pour l’activité en ligne.
  
> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online. Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REPLACER L’UTILISATEUR DANS VOTRE ENVIRONNEMENT LOCAL.
Si la réinitialisation matérielle est effectuée avant l’installation du microprogramme minimal requis sur l’appareil, celui-ci utilise par défaut l’authentification par code confidentiel, ce qui n’est pas pris en charge par Skype Entreprise Online. Pour plus d’informations, reportez-vous à la [Mise en route de téléphones pour Skype pour l’activité en ligne](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Il s’agit d’une étape facultative qui est uniquement nécessaire si vous déplacez les utilisateurs locaux à Skype pour l’activité en ligne. Avant de commencer à déplacer les utilisateurs vers Skype pour entreprise en ligne, vérifiez que le Skype pour connecteur de Business Online (module de Windows PowerShell) est déployée sur vos serveurs frontaux. Si elle n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Par ailleurs, pour préparer votre AD, vous devez configurer Azure AD Connect. La version d’AAD Connect que vous utilisez doit être de version 1.0.9125.0 ou version ultérieure. Si vous utilisez des outils d'une version antérieure d’AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement.
  
Vous déplacez des utilisateurs à l’aide soit Skype pour panneau de commande du serveur Business ou Skype pour Business Server Management Shell dans votre déploiement sur site, mais vous devez disposer des informations d’identification de l’administrateur pour votre déploiement d’Office 365.
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>Déplacement d’utilisateurs à l’aide de Skype pour panneau d’entreprise

### <a name="to-move-a-user-to-skype-for-business-online"></a>Pour atteindre un utilisateur Skype pour professionnels en ligne

1. À partir d’un compte d’utilisateur qui est affecté à la rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne qui a Skype pour Business Server ou, au moins Skype pour les outils d’administration du serveur Business installé.
    
2. À partir du menu Démarrer ou d’un raccourci sur le bureau, ouvrez le Skype pour le panneau de configuration de Business Server.
    
    Vous pouvez également accéder le Skype pour le panneau de configuration de Business Server à l’aide de l’URL d’administration si vous avez configuré un.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Cliquez sur l’utilisateur, puis, dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers Skype Entreprise Online**.
    
6. Dans la page **Déplacer des utilisateurs vers Skype Entreprise Online**, lisez les informations, puis cliquez sur **Suivant**.
    
7. Sur la page suivante, si vous n’êtes pas encore connecté à Office 365, cliquez sur **se connecter à Office 365**, vos informations d’identification et cliquez sur **OK** et sur **suivant**.
    
8. Confirmez que le nombre d’utilisateurs à déplacer est correct, puis cliquez sur **Suivant**.
    
9. Dans la page suivante, vérifiez les résultats et cliquez sur **Fermer**.
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Déplacement d’utilisateurs à l’aide de Skype pour Business Server Management Shell

Pour déplacer un utilisateur local vers votre Skype pour clients d’entreprise en ligne, exécuter les applets de commande suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour vos clients de Microsoft Office 365. Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant : _Https://\<nom de domaine complet Pool\>/HostedMigration/ hostedmigrationService.svc_.
  
Vous pouvez déterminer l’URL pour le Service hébergé de la Migration en consultant l’URL pour le Skype pour le centre d’administration en ligne de Business pour votre compte de clients Office 365.
  
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
    
    L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

