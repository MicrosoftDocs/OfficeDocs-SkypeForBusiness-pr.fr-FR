---
title: Déployer une apparence de ligne partagée dans Skype entreprise Server 2015
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
description: Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans la mise à jour cumulative de Skype entreprise Server 2015, novembre 2015. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604221"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Déployer une apparence de ligne partagée dans Skype entreprise Server 2015

Consultez cette rubrique pour découvrir comment déployer l’apparence de ligne partagée (SLA) dans la mise à jour cumulative de Skype entreprise Server 2015, novembre 2015. Le contrat SLA est une fonctionnalité permettant de gérer plusieurs appels sur un numéro spécifique appelé « numéro partagé ».

Pour plus d’informations sur cette fonctionnalité, reportez-vous à la rubrique [plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

L’apparence de ligne partagée (SLA) est une nouvelle fonctionnalité de Skype entreprise Server, mise à jour cumulative de novembre 2015. Pour activer cette fonctionnalité, vous devez d’abord déployer cette mise à jour cumulative.

### <a name="install-shared-line-appearance"></a>Installation de l’apparence des lignes partagées

1. Après le déploiement de la mise à jour cumulative de Skype entreprise Server, novembre `SkypeServerUpdateInstaller.exe` 2015, exécutez le correctif sur chaque serveur frontal du pool.

2. Le programme d’installation déploiera la dernière version de l’application SLA, mais l’application n’est pas activée par défaut. Pour l’activer, procédez comme suit :

    a. Inscrivez le contrat SLA en tant qu’application serveur en exécutant la commande suivante pour chaque pool :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   où% FQDN% est le nom de domaine complet du pool.

    b. Exécutez la commande suivante pour mettre à jour les rôles RBAC pour les cmdlets SLA :

   ```powershell
   Update-CsAdminRole
   ```

    c. Redémarrez tous les serveurs frontaux (RTCSRV service) dans tous les pools où le contrat SLA a été installé et activé :

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Créer un groupe de SLA et y ajouter des utilisateurs

1. Créez le groupe SLA à l’aide de l’applet de commande [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    La cmdlet Set-CsSlaConfiguration marque le compte voix entreprise SLAGroup1 comme entité SLA et le nombre d’SLAGroup1 devient le numéro du groupe SLA. Tous les appels vers SLAGroup1 sonneront dans l’ensemble du groupe SLA.

    L’exemple suivant crée un groupe de SLA pour un utilisateur voix entreprise existant, SLAGroup1, et utilise le numéro attribué à SLAGroup1 comme numéro de la forme de service SLA.

    La commande définit le nombre maximal d’appels simultanés pour le nouveau groupe de SLA sur 3, et pour les appels au-delà de celui pour écouter un signal occupé :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Vous pouvez utiliser SET-CsSlaConfiguration pour créer un nouveau groupe de SLA ou en modifier un existant.

    > [!NOTE]
    > Notez que ce que vous spécifiez pour doit être un compte d’utilisateur activé pour `-Identity` voix entreprise existant valide.

2. Ajoutez des délégués au groupe à l’aide de la cmdlet [Add-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    L’exemple suivant ajoute un utilisateur au groupe SLA. Chaque utilisateur ajouté au groupe doit être un utilisateur compatible voix entreprise valide :

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Répétez l’applet de commande pour chaque utilisateur que vous souhaitez ajouter au groupe. Les utilisateurs ne peuvent appartenir qu’à un seul groupe SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurer l’option de disponibilité du groupe SLA

- Configurez l’option de disponibilité du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L’exemple suivant définit les appels qui dépassent le nombre maximal d’appels simultanés à transmettre au numéro de téléphone 202-555-1234. La cible peut être un utilisateur de votre organisation au lieu d’un numéro de téléphone ; dans ce cas, la syntaxe de la personne qui reçoit les appels transférés est la même que lorsque vous spécifiez un délégué `sip:<NameofDelegate@domain>`:. L’autre paramètre possible pour `BusyOption` est `Voicemail`le suivant :

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurer l’option d’appel manqué du groupe SLA

1. Configurez l’option d’appel manqué du groupe SLA à l’aide de la cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. L’exemple suivant spécifie que les appels manqués doivent être transférés à l' `sla_forward_number`utilisateur nommé. Les options valides pour `-MissedCallOption` le paramètre `Forward`sont `BusySignal`, ou `Disconnect`. Si vous le `Forward`souhaitez, vous devez également inclure `-MissedCallForwardTarget` le paramètre, avec un utilisateur ou un numéro de téléphone comme cible :

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Supprimer un délégué d’un groupe

- Supprimer un délégué d’un groupe à l’aide de l’applet de commande [Remove-applet cssladelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Supprimer un groupe SLA

- Supprimez un groupe de SLA à l’aide de l’applet de commande [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Par exemple :

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


