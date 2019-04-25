---
title: Communiquer avec des utilisateurs de Teams dans une autre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Découvrez comment configurer des équipes pour permettre aux utilisateurs de communiquer avec les utilisateurs d’une autre organisation.
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222370"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes

Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs dans des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation d’utiliser des équipes pour contacter les personnes figurant dans les entreprises spécifiques à l’extérieur de votre organisation.
    
- Vous souhaitez quiconque dans le monde qui utilise des équipes pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie. Si vous et un autre utilisateur Activer l’accès externe et autoriser les domaines de l’autre, cela fonctionnera. Si elle ne fonctionne pas, l’autre utilisateur devez vous assurer que son ou sa configuration n’est pas le blocage de votre domaine.

Cela permettra aux utilisateurs de rechercher, appeler et vous envoyer des messages instantanés, mais aussi définir des réunions avec vous. Si vous souhaitez que les utilisateurs externes d’accéder aux équipes et les canaux, accès invité peut être une meilleure façon pour accéder. Suivez les étapes décrites dans cet article et les Assurez-vous pour [Activer l’accès invité](set-up-guests.md) afin que les utilisateurs peuvent communiquer.

> [!IMPORTANT]
> Afin de vous fédérer actuellement dans le client Microsoft Teams à un utilisateur externe à l’extérieur de votre organisation qui n’est pas invité de votre DAS/client, vous devez être correctement configuré pour l’environnement hybride et déplacée vers Skype pour Business Online. 25/2/2019, équipes n’encore prennent en charge native fédération sans que l’utilisateur du profil SIP en cours hébergé dans Skype pour Business Online. Pour plus d’informations sur la configuration de configurer votre compte pour l’environnement hybride et ensuite vers les équipes, consultez [Mise à niveau de Skype pour un déploiement hybride Business aux équipes](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes

Suivez ces étapes.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Étape 1 : veillez à configurer les ports et les URL qui sont nécessaires.

**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 2 : activer votre organisation de communiquer avec une autre organisation d’équipes

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

   1. Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **l’accès externe**. 

   2. En haut de la page **d’accès externe** , cliquez sur **accès externe** **activé**. 

   3. Si vous souhaitez autoriser toutes les organisations d’équipes de communiquer avec les utilisateurs de votre organisation, passez à l’étape 5. 
   
   4. Si vous souhaitez limiter les organisations peuvent communiquer avec les utilisateurs de votre organisation vous pouvez autoriser tous les mais certains domaines ou autoriser uniquement les organisations spécifiques. Pour autoriser tous les mais certains domaines, ajoutez les domaines que vous souhaitez bloquer en cliquant sur **Ajouter domaine**. Dans le volet **Ajouter un domaine** , placez le nom de domaine, cliquez sur **bloqué** , puis sur **terminé**. Pour limiter les communications à organizatioins spécifique, ajoutez ces domaines à la liste avec l’état **Alowed**. Une fois que vous avez ajouté un domaine à la liste verte, les communications à d’autres organisations seront limitées pour que les organisations dont les domaines sont dans la liste verte. 
   
   5. Cliquez sur **Enregistrer**. 

   6. Vérifiez que l’administrateur de l’autre organisation équipes est ces étapes. Par exemple, dans leur liste des **domaines autorisés** , leur administrateur a besoin d’entrer le domaine de votre entreprise si elles définir les organisations peuvent communiquer avec leurs utilisateurs. 

### <a name="step-3---test-it"></a>Étape 3 : tester
Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipes qui n’est pas derrière votre pare-feu.
  
   1. Une fois que l’administration de l’organisation et vous ont modifié les paramètres **d’accès externe** , vous devez être bon.
    
   2. Dans l’application d’équipes, rechercher la personne à l’adresse de messagerie et envoyer une requête à la conversation.
    
   3. Demandez à votre contact équipes vous envoyer une demande à la conversation. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
   4. Une autre manière de tester si le problème est votre pare-feu consiste à accéder à un emplacement Wi-Fi pas derrière votre pare-feu comme un café et équipes permet d’envoyer une demande à votre contact à la conversation. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquer avec les utilisateurs dans un Skype pour une organisation Business en ligne

Si vous le configurez pour laisser votre recherche d’utilisateurs équipes et les contacts des utilisateurs qui se trouvent dans un Skype pour l’organisation de l’entreprise qui limite qui peut contacter leurs utilisateurs, vous allez demander à l’administrateur dans cette organisation, procédez comme suit.

![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de Skype entreprise centre d’administration** 

Disposer de l’administrateur dans cette organisation procédez comme suit :
    
1. Dans le centre d’administration Office 365, accédez au **Centre d’administration** > **& équipes Skype** > **portail hérité**.
  
2. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
    
3. Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.
    
    OU, s’il souhaite permettre la communication avec tout le monde dans le monde qui a ouvert Skype pour les stratégies d’entreprise, choisissez **sur à l’exception des domaines bloqués**. Il s’agit du paramètre par défaut.
    
4. Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser. Assurez-vous que l’administrateur de l’autre organisation est la même procédure. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
### <a name="related-topics"></a>Voir aussi

[Se connecter à Microsoft Teams](sign-in-teams.md)
[utilisateur final de formation pour les équipes](enduser-training.md)

