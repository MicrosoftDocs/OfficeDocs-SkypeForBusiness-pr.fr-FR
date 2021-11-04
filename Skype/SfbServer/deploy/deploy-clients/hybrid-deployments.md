---
title: Skype Déploiements hybrides du système de salle
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.
ms.openlocfilehash: c47809fcf5277ed34f11955b19306e6a4078d650
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751353"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Déploiements hybrides du système de salle

Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.
  
## <a name="hybrid-deployments"></a>Déploiements hybrides

Suivez ces étapes si votre topologie dispose de Skype Entreprise Server et Exchange Online et que vous souhaitez héberger la boîte aux lettres de ressources Skype Room System sur Exchange Online. Cette section couvre également un scénario hybride dans lequel vous avez déployé Exchange Online et Exchange Server déploiement.
  
À titre d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.
  
1. Créez une boîte aux lettres de ressources dans Exchange centre d’administration (LyncSample.ccsctp.net) en vous connectant à l’environnement de ligne de Exchange Online Management Shell, comme décrit dans Exchange Online approvisionnement.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Vous pouvez vérifier la connectivité OWA à l’aide lrstest5@LyncSample.ccsctp.net pour vous connecter.
    
2. Dans le Microsoft 365 ou Office 365 Exchange’administration, ajoutez une adresse de messagerie lrstest5@LyncSample.com (domaine sur site) et définissez-la comme adresse de réponse.
    
3. Créez une lrstest5@LyncSample.com utilisateur Active Directory sur site, définissez l’adresse de messagerie sur lrstest5@LyncSample.com et définissez l’adresse cible sur lrstest5@LyncSample.com.
    
4. Déclenchez la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs fusionnent dans AAD et que vous ne pouvez pas modifier les propriétés des ressources du destinataire dans le Centre d’administration Microsoft 365 ou Office 365 Exchange.
    
5. Vérifiez OWA connectivité à l’aide lrstest5@LyncSample.com. (Précédemment, vous avez vérifié OWA à l’aide du domaine en ligne.)
    
    Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing sur le Exchange Online Management Shell pour configurer la boîte aux lettres. Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous Déploiements sur site à forêt unique.
    
   > [!NOTE]
   > Si vous avez un environnement hybride avec Exchange Server et Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Déclenchez ensuite la synchronisation d’annuaires. 
  
    Si vous souhaitez héberger la boîte aux lettres Skype Room System dans Exchange Online, ces étapes Exchange Management Shell ne sont pas requises et vous pouvez passer à l’étape 6.
    
6. Activez le compte Skype Room System pour Skype Entreprise en exécutant l’cmdlet suivante sur Skype Entreprise Management Shell :
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si vous avez Skype Entreprise Online au lieu de Skype Entreprise Server dans le scénario ci-dessus, une fois la boîte aux lettres de ressources Exchange mise en service, vous devez mettre en service un compte Skype Entreprise comme décrit dans Skype Entreprise Online Approvisionnement. 
  

