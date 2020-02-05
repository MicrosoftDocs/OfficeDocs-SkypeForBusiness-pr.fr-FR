---
title: Déploiement du mode partage de lignes dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».
ms.openlocfilehash: c9c4eef43de2f03be32e92c23e8384020e24b099
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767507"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Déploiement du mode partage de lignes dans Skype Entreprise Server 2015

Pour découvrir comment déployer le mode partage de lignes dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015, reportez-vous à cette rubrique. Le mode partage de lignes est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».

Pour plus d’informations sur cette fonctionnalité, reportez-vous à la rubrique [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

L’apparence des lignes partagées (SLA) est une nouvelle fonctionnalité de la mise à jour cumulative 2015 de novembre Server. Pour activer cette fonctionnalité, vous devez d’abord avoir déployé cette mise à jour cumulative.

### <a name="install-shared-line-appearance"></a>Installation du mode partage de lignes

1. Après le déploiement de Skype entreprise Server, la mise à jour cumulative 2015 de `SkypeServerUpdateInstaller.exe` novembre, exécutez le correctif sur chaque serveur frontal du pool.

2. Le programme d’installation déploiera la version la plus récente de l’application Mode partage de lignes, mais l’application n’est pas activée par défaut. Elle est activée en suivant la procédure décrite ci-dessous :

    a. Enregistrez le mode partage de lignes comme application serveur en exécutant la commande ci-dessous pour chaque pool :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   où %FQDN% est le nom de domaine complet du pool.

    b. Exécutez la commande ci-dessous pour mettre à jour les rôles RBAC pour les applets de commande du mode partage de lignes :

   ```powershell
   Update-CsAdminRole
   ```

    c. Redémarrez tous les serveurs frontaux (service RTCSERV) dans tous les pools où le mode partage de lignes a été installé et activé :

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Créez un groupe de mode partage de lignes et ajoutez-y des utilisateurs.

1. Créez le groupe de mode partage de lignes à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    L’applet de commande Set-CsSlaConfiguration marque le compte SLAGroup1 de Voix Entreprise en tant qu’entité de mode partage de lignes, et le numéro de SLAGroup1 devient le numéro du groupe de mode partage de lignes. Tous les appels vers SLAGroup1 sonneront chez l’ensemble du groupe de mode partage de lignes.

    L’exemple ci-dessous crée un groupe de mode partage de lignes pour un utilisateur Voix Entreprise existant, SLAGroup1, et utilise le numéro attribué pour SLAGroup1 comme numéro de ligne principale du mode partage de lignes.

    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de mode partage de lignes sur 3. Les appels qui dépassent cette limitent entendront une tonalité Occupé :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Vous pouvez utiliser Set-CsSlaConfiguration pour créer un groupe de mode partage de lignes ou modifier un groupe existant.

    > [!NOTE]
    > Notez que ce que vous spécifiez pour doit être un compte d’utilisateur valide pour `-Identity` la voix entreprise valide.

2. Ajoutez des délégués au groupe à l’aide de l’applet de commande [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    L’exemple ci-dessous permet d’ajouter un utilisateur au groupe de mode partage de lignes. Chaque utilisateur ajouté au groupe doit être un utilisateur valide d’entreprise Voice :

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Répétez l’applet de commande pour chaque utilisateur que vous voulez ajouter au groupe. Les utilisateurs peuvent seulement appartenir à un seul groupe de mode de partage de lignes.

### <a name="configure-the-sla-group-busy-option"></a>Configuration de l’option Occupé du groupe de mode partage de lignes

- Configurez l’option Occupé du groupe de mode partage de lignes à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transférer vers le numéro de téléphone 202-555-1234. La cible peut être un utilisateur au sein de votre organisation plutôt qu’un numéro de téléphone. dans ce cas, la syntaxe de la personne qui reçoit les appels transférés est la même que lorsque vous spécifiez un délégué `sip:<NameofDelegate@domain>`:. Le autre paramètre possible pour `BusyOption` est `Voicemail`le suivant :

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configuration de l’option Appel manqué du groupe de mode partage de lignes

1. Configurez l’option Appel manqué du groupe de mode partage de lignes à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. L’exemple suivant spécifie que les appels manqués doivent être renvoyés à `sla_forward_number`l’utilisateur nommé. Les options valides pour `-MissedCallOption` le paramètre `Forward`sont `BusySignal`, ou `Disconnect`. Si vous le `Forward`souhaitez, vous devez également inclure `-MissedCallForwardTarget` le paramètre, avec un utilisateur ou un numéro de téléphone comme destination :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Suppression d’un délégué d’un groupe

- Supprimez un délégué d’un groupe à l’aide de l’applet de commande [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Suppression d’un groupe de mode partage de lignes

- Supprimez un groupe de mode partage de lignes à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


