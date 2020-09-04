---
title: Activer la messagerie vocale pour les utilisateurs de la messagerie vocale Enterprise Online et du système téléphonique
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer les services vocaux de téléphonie pour vos utilisateurs de Skype entreprise.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359180"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Activer la messagerie vocale pour les utilisateurs de la messagerie vocale Enterprise Online et du système téléphonique
 
> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.  De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Découvrez comment activer les services vocaux de téléphonie pour vos utilisateurs de Skype entreprise.
  
La dernière étape du déploiement d’un système téléphonique avec une connectivité RTC sur site consiste à activer vos utilisateurs pour le système téléphonique et la messagerie vocale. Pour activer ces fonctionnalités, vous devez être un utilisateur doté du rôle d’administrateur général et être en mesure d’exécuter PowerShell à distance. Vous devez suivre les étapes décrites dans cette rubrique pour tous les comptes d’utilisateur pour lesquels la fonctionnalité voix entreprise n’est pas encore activée pour Skype entreprise online.
  
## <a name="enable-phone-system-voice-services"></a>Activer les services vocaux de système téléphonique

Pour activer un utilisateur pour la voix et la messagerie vocale du système téléphonique, vous devez effectuer certaines opérations initiales, comme vérifier si le connecteur Skype entreprise Online est déployé sur vos serveurs et activer la messagerie vocale hébergée pour vos utilisateurs.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Pour activer les utilisateurs pour la voix et la messagerie vocale du système téléphonique

1. Avant de commencer, vérifiez que le connecteur Skype entreprise Online (module Windows PowerShell) est déployé sur vos serveurs frontaux. Si ce n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/download/details.aspx?id=39366). Vous trouverez plus d’informations sur l’utilisation de ce module dans [la rubrique Configuration de votre ordinateur pour la gestion de Skype entreprise Online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).
    
2. Démarrez Windows PowerShell en tant qu’administrateur.
    
3. Tapez la commande ci-dessous, puis appuyez sur entrée :
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Tapez la commande ci-dessous, puis appuyez sur entrée :
    
   ```powershell
   $cred = Get-Credential
   ```

    Une fois que vous avez appuyé sur entrée, la boîte de dialogue informations d’identification Windows PowerShell doit s’afficher.
    
5. Tapez le nom d’utilisateur et le mot de passe de votre administrateur client, puis cliquez sur **OK**.
    
6. Dans la fenêtre PowerShell, tapez la commande suivante, puis appuyez sur entrée :
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importez la session en tapant l’applet de commande suivante :
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Lors de l’exécution de PowerShell sur un serveur Skype entreprise, les applets de commande locales de Skype entreprise sont déjà chargées lorsque vous ouvrez PowerShell. Vous devez spécifier le paramètre-AllowClobber pour permettre aux cmdlets en ligne de remplacer les applets de commande locales portant le même nom.
    
8. Utilisez l’applet de commande Set-CsUser pour affecter les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Par exemple :
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Vous pouvez également spécifier un utilisateur par son adresse SIP, nom d’utilisateur principal (UPN), nom de domaine et nom d’utilisateur (domaine\nom_utilisateur), et le nom d’affichage dans Active Directory (« Bob Kelly »). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique

Cette section décrit comment mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique. 
  
### <a name="to-update-the-line-uri"></a>Pour mettre à jour l’URI de ligne

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci Bureau pour ouvrir le panneau de configuration de Skype entreprise Server.
    
    > [!NOTE]
    > Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le panneau de configuration de Skype entreprise Server. 
  
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur Skype entreprise dont vous souhaitez modifier l’URI de ligne.
    
6. Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tel : + 14255550200). Ensuite, cliquez sur **valider**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Mettre à jour le plan de numérotation à l’aide des applets de commande Windows PowerShell locales

Vous pouvez attribuer des plans de numérotation par utilisateur avec Windows PowerShell et l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server 2015 ou d’une session distante de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Pour affecter un plan de numérotation par utilisateur à un seul utilisateur

- Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour affecter le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer :
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs

- La commande suivante attribue le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Vous pouvez utiliser des plans de numérotation de type utilisateur ou global pour les utilisateurs en ligne. Les plans de numérotation de site ne peuvent pas être utilisés car ils s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Pour annuler l’affectation d’un plan de numérotation par utilisateur

- Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour annuler l’affectation d’un plan de numérotation par utilisateur précédemment affecté à Ken Myer. Une fois que le plan de numérotation par utilisateur n’est pas affecté, Ken Myer est automatiquement géré à l’aide du plan de numérotation global ou du plan de numérotation de l’étendue service affecté à son serveur d’inscriptions ou à sa passerelle RTC. Un plan de numérotation d’étendue de service est prioritaire sur le plan de numérotation global :
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Mettre à jour les stratégies de routage des communications vocales à l’aide des applets de commande locales Windows PowerShell

Cette section décrit comment mettre à jour les stratégies de routage des communications vocales pour les utilisateurs activés pour le système téléphonique.
  
Les utilisateurs du système téléphonique doivent disposer d’une stratégie de routage des communications vocales pour que les appels soient acheminés correctement. Il en est de même pour les utilisateurs de voix entreprise sur site qui nécessitent une stratégie de voix qui leur est attribuée pour permettre l’acheminement des appels. La stratégie de routage des communications vocales doit contenir des utilisations PSTN qui définissent les appels et itinéraires autorisés pour les utilisateurs du système téléphonique. Vous pouvez copier ces utilisations RTC à partir des stratégies de voix existantes vers les nouvelles stratégies de routage des communications vocales. Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Tous les utilisateurs du système téléphonique sont affectés à la même stratégie de voix en ligne nommée BusinessVoice qui définit les fonctionnalités d’appel autorisées ; par exemple, autoriser les sonneries simultanées. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à un seul utilisateur

- Utilisez l’applet de commande [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour affecter la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à l’utilisateur Ken Myer :
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Pour affecter une stratégie de routage des communications vocales par utilisateur à plusieurs utilisateurs

- La commande suivante attribue la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, consultez la rubrique [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Vous pouvez utiliser des stratégies de routage des communications vocales ou globales pour les utilisateurs en ligne. Les stratégies de routage des communications vocales du site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur

- Utilisez Grant-CsVoiceRoutingPolicy pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur précédemment affectée à Ken Myer. Une fois la stratégie de routage des communications vocales par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale de routage des communications vocales.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Pour plus d’informations, consultez la rubrique [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

