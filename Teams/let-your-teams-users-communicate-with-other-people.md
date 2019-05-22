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
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Découvrez comment configurer teams pour permettre aux utilisateurs de communiquer avec des utilisateurs d’une autre organisation.
ms.openlocfilehash: 5da04eec6b8ce643f32639a014237ffe118aeabe
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34343937"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permettre aux utilisateurs d’équipes de discuter et de communiquer avec les utilisateurs d’une autre organisation teams

Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs dans différents domaines au sein de votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous voulez que les membres de votre organisation puissent utiliser teams pour contacter des personnes dans des entreprises spécifiques en dehors de votre organisation.
    
- Vous voulez que les autres personnes qui utilisent des équipes puissent vous trouver et vous contacter à l’aide de votre adresse de messagerie. Par ailleurs, si vous et un autre utilisateur autorisez l’accès externe et autorisez les domaines de chacun d’eux, cela va fonctionner. Si ce n’est pas le cas, l’autre utilisateur doit veiller à ce qu’il ne bloque pas votre domaine.

Cela permet aux utilisateurs de rechercher, appeler et envoyer des messages instantanés, ainsi que de configurer des réunions avec vous. Si vous souhaitez que les utilisateurs externes aient accès à des équipes et des canaux, l’accès invité peut être une meilleure solution. Suivez les étapes décrites dans cet article et assurez-vous d' [activer l’accès invité](set-up-guests.md) pour que les utilisateurs puissent communiquer.

> [!IMPORTANT]
> Pour que vous puissiez actuellement fédérer le client Microsoft teams à un utilisateur externe extérieur à votre organisation qui n’est pas un invité de votre client AAD ou de votre client, vous devez être correctement configuré pour l’environnement hybride et transféré vers Skype entreprise online. À partir de 2/25/2019, Teams ne prend pas encore en charge la Fédération native sans que l’utilisateur du profil SIP ne soit hébergé dans Skype entreprise online. Pour plus d’informations sur la configuration de votre compte hybride, puis celle-ci, reportez-vous à la rubrique [mise à niveau du déploiement hybride de Skype entreprise vers teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permettre aux utilisateurs d’équipes de discuter et de communiquer avec les utilisateurs d’une autre organisation teams

Procédez comme suit.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Étape 1: Veillez à configurer les ports et les URL nécessaires.

**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 2: permettre à votre organisation de communiquer avec d’autres organisations teams

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

   1. Dans le volet de navigation de gauche, accédez à**accès externe aux** **paramètres** > à l’échelle de l’organisation. 

   2. En haut de la page **accès externe** , cliquez sur **accès externe** à **activé**. 

   3. Si vous voulez autoriser toutes les organisations teams à communiquer avec les utilisateurs de votre organisation, passez à l’étape 5. 
   
   4. Si vous souhaitez limiter les organisations qui peuvent communiquer avec des utilisateurs de votre organisation, vous pouvez autoriser tous les domaines sauf quelques domaines ou autoriser des organisations spécifiques uniquement. Pour autoriser tout sauf quelques domaines, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**. Dans le volet **Ajouter un domaine** , indiquez le nom de domaine, puis cliquez sur **bloqué** puis sur **Terminer**. Pour limiter les communications à des organizatioins spécifiques, ajoutez ces domaines à la liste avec un statut de **créance**. Une fois que vous avez ajouté un domaine à la liste verte, les communications vers d’autres organisations sont limitées uniquement aux organisations dont le domaine figure dans la liste verte. 
   
   5. Cliquez sur **Enregistrer**. 

   6. Assurez-vous ensuite que l’administrateur de l’organisation autres équipes effectue les mêmes étapes. Par exemple, dans la liste de **domaines autorisés** , l’administrateur doit entrer le domaine de votre entreprise s’il limite les organisations qui peuvent communiquer avec leurs utilisateurs. 

### <a name="step-3---test-it"></a>Étape 3: test
Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipe qui ne se trouve pas derrière votre pare-feu.
  
   1. Lorsque votre administrateur et vous-même avez modifié les paramètres d' **accès externe** , il est conseillé de procéder comme suit.
    
   2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de discussion.
    
   3. Demandez à votre contact teams de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
   4. Un autre moyen de tester s’il s’agit d’un problème lié à votre pare-feu consiste à accéder à un point d’accès WiFi qui ne se trouve pas sur votre pare-feu (par exemple, un café) et à utiliser teams pour envoyer une demande de discussion à votre contact. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquer avec des utilisateurs dans une organisation Skype entreprise Online

Si vous le configurez de manière à permettre aux utilisateurs de teams de rechercher et de contacter des utilisateurs de l’organisation Skype entreprise qui limitent les personnes qui peuvent contacter leurs utilisateurs, vous devez demander à l’administrateur de l’organisation de suivre ces étapes.

![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **avec le centre d’administration Skype entreprise** 

Demandez à l’administrateur de l’organisation de procéder comme suit:
    
1. Dans le centre d’administration Office 365, accédez à centre d' **administration** > **teams &** > le**portail hérité**de Skype.
  
2. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
    
3. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.
    
    Pour permettre à tous les utilisateurs du monde entier de communiquer entre eux, choisissez **activé sauf pour les domaines bloqués**. Il s’agit du paramètre par défaut.
    
4. Sous **domaines bloqués ou autorisés**, **+** sélectionnez et ajoutez le nom du domaine que vous voulez autoriser. Assurez-vous que l’administrateur de l’autre organisation effectue les mêmes étapes. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
### <a name="related-topics"></a>Voir aussi

[Se connecter à](sign-in-teams.md)
la formation de l'[utilisateur final de](enduser-training.md) Microsoft teams pour teams

