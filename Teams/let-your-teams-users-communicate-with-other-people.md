---
title: Communiquer avec les utilisateurs d’équipes dans une autre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Découvrez comment configurer des équipes pour permettre aux utilisateurs de communiquer avec les utilisateurs d’une autre organisation.
ms.openlocfilehash: 3eaffac3571abc70d4964ea4a8955f187d1e988f
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844636"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes

Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs dans des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation d’utiliser des équipes pour contacter les personnes figurant dans les entreprises spécifiques à l’extérieur de votre organisation.
    
- Vous souhaitez quiconque dans le monde qui utilise des équipes pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie. Si vous et un autre utilisateur Activer l’accès externe et autoriser les domaines de l’autre, cela fonctionnera. Si elle ne fonctionne pas, l’autre utilisateur devez vous assurer que son ou sa configuration n’est pas le blocage de votre domaine.

Procédez comme suit :

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Étape 1 : veillez à configurer les ports et les URL qui sont nécessaires.

**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 2 : activer votre organisation de communiquer avec une autre organisation d’équipes

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

   1. Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **l’accès externe**. 

   2. En haut de la page **d’accès externe** , cliquez sur **accès externe** **activé**. 

   3. Ajouter le domaine de l’autre organisation à la liste autorisée en cliquant sur **Ajouter domaine**. Dans le volet **Ajouter un domaine** , placez dans le domaine, cliquez sur nom **autorisé** , puis sur **terminé**.

   4. Cliquez sur **Enregistrer**. 

   5. Vérifiez que l’administrateur de l’autre organisation équipes est ces étapes. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.

### <a name="step-3---test-it"></a>Étape 3 : tester
Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipes qui n’est pas derrière votre pare-feu.
  
   1. Une fois que l’administration de l’organisation et vous ont modifié les paramètres **d’accès externe** , vous devez être bon.
    
   2. Dans l’application d’équipes, rechercher la personne à l’adresse de messagerie et envoyer une requête à la conversation.
    
   3. Demandez à votre contact équipes vous envoyer une demande à la conversation. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
   4. Une autre manière de tester si le problème est votre pare-feu consiste à accéder à un emplacement Wi-Fi pas derrière votre pare-feu comme un café et équipes permet d’envoyer une demande à votre contact à la conversation. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquer avec les utilisateurs dans un Skype pour une organisation Business en ligne

Si vous le configurez jusqu'à let vos utilisateurs équipes rechercher et contacter les utilisateurs qui se trouvent dans un Skype pour l’organisation de l’entreprise, vous serez l’administrateur dans cette organisation, procédez comme suit.

![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de Skype entreprise centre d’administration** 

Disposer de l’administrateur dans cette organisation procédez comme suit :
    
1. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.
  
2. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
    
3. Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.
    
    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.
    
4. Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser. Assurez-vous que l’administrateur de l’autre organisation est la même procédure. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
### <a name="related-topics"></a>Rubriques connexes

[Connecter les équipes](sign-in-teams.md)
[utilisateur final de formation pour les équipes](enduser-training.md)

