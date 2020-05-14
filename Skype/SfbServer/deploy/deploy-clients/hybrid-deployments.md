---
title: Déploiements hybrides de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219674"
---
# <a name="skype-room-system-hybrid-deployments"></a>Déploiements hybrides de Skype Room System

Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.
  
## <a name="hybrid-deployments"></a>Déploiements hybrides

Procédez comme suit si votre topologie comporte Skype entreprise Server et Exchange Online, et que vous voulez héberger la boîte aux lettres de ressources Skype Room System sur Exchange Online. Cette section couvre également un scénario hybride dans lequel vous avez déployé Exchange Online et Exchange Server.
  
À des fins d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.
  
1. Créez une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) en vous connectant à Exchange Online Management Shell comme décrit dans Exchange Online Provisioning.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Vous pouvez vérifier la connectivité OWA à l’aide de lrstest5@LyncSample.ccsctp.net pour vous connecter.
    
2. Dans le centre d’administration Exchange de Microsoft 365 ou Office 365, ajoutez une adresse de messagerie lrstest5@LyncSample.com (domaine local) et définissez-la comme adresse de réponse.
    
3. Créez un lrstest5@LyncSample.com d’utilisateur Active Directory sur local, définissez l’adresse de messagerie sur lrstest5@LyncSample.com et définissez l’adresse cible sur lrstest5@LyncSample.com.
    
4. Déclenchez la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs fusionnent dans AAD et que vous ne pouvez pas modifier les propriétés dans les ressources du destinataire dans le centre d’administration Exchange de Microsoft 365 ou d’Office 365.
    
5. Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com. (Précédemment, vous avez vérifié la connectivité OWA à l’aide du domaine en ligne.)
    
    Après avoir créé la boîte aux lettres, vous pouvez utiliser SET-CalendarProcessing sur Exchange Online Management Shell pour configurer la boîte aux lettres. Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous déploiements de forêt unique sur-local.
    
   > [!NOTE]
   > Si vous disposez d’un environnement hybride avec Exchange Server et Exchange Online, accédez à l’environnement de ligne de commande Exchange Management Shell et activez-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. Puis déclenchez la synchronisation d’annuaires. 
  
    Si vous voulez héberger la boîte aux lettres de Skype Room System dans Exchange Online, ces étapes de l’environnement de ligne de commande Exchange Management Shell ne sont pas requises et vous pouvez passer à l’étape 6.
    
6. Activez le compte Skype Room System pour Skype entreprise en exécutant l’applet de commande suivante sur Skype entreprise Management Shell :
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous avez Skype entreprise Online au lieu de Skype entreprise Server dans le scénario ci-dessus, après avoir configuré la boîte aux lettres de ressources Exchange, configurez un compte Skype entreprise comme décrit dans Skype entreprise Online Provisioning. 
  

