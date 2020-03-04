---
title: Prise en charge des travailleurs à distance avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: Utilisez les conseils ci-dessous pour améliorer la productivité des employés de votre organisation en utilisant Microsoft Teams, en particulier lorsqu’ils travaillent à partir de chez eux (WFH) en réponse à l’épidémie COVID-19 (coronavirus).
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374311"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Prise en charge des travailleurs à distance avec Microsoft Teams

Utilisez les pratiques recommandées décrites dans cet article pour soutenir les utilisateurs qui travaillent à distance ou à partir de leur domicile.

## <a name="technical"></a>Technique

1.  Assurez-vous que [Teams est activé pour tout le monde](assign-teams-licenses.md)
    
      - Consultez la [Version d’essai de Teams E1](e1-trial-license.md), l’[expérience exploratoire de Teams](teams-exploratory.md), ou la [Version gratuite de Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) pour mettre Teams à la disposition de tous les membres de votre équipe.

      - Les employés à distance dépendent plus largement des réunions et des conférences audio. Si vous n’avez pas encore déployé ces charges de travail, consultez les [Réunions et conférences dans Teams](deploy-meetings-microsoft-teams-landing-page.md).

2.  Présentez Teams à vos utilisateurs. Téléchargez le [Kit de réussite du client Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) pour obtenir des présentations, des exemples de courriers électroniques, des affiches et des guides de mise en route.


5.  Vous assurer que vos employés disposent d'un accès internet approprié et de la bande passante pour Teams. Pour plus d’informations sur la procédure, suivez les recommandations de [Préparer le réseau de votre organisation pour Teams](prepare-network.md).
    - Une bande passante restreinte peut avoir une incidence sur la qualité audio des réunions dans Teams. Afin de garantir une expérience de réunion optimale dans des conditions de bande passante faible, encouragez les utilisateurs à limiter la vidéo et à utiliser PSTN pour les appels et les conférences audio. 

    - Si vous avez besoin d’aide pour résoudre des problèmes de qualité d’appel ou de réunion, suivez les instructions de [Problème connu : numérotation dans les ID de conférence Skype Entreprise/Teams](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) au bas de cet article.

2.  [Envoyez des liens vers des formations](enduser-training.md) pour aider vos employés à tirer le meilleur parti de Teams.
    
3. Lisez notre nouveau contenu sur le travail à distance et partagez-le avec vos utilisateurs :
        
      - Blog Teams (28 février 2020) : [4 astuces pour travailler avec Microsoft Teams depuis chez vous](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Collaborez avec Office 365](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Le travail à distance avec Teams et Office 365](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  Encouragez chaque personne à [installer](get-clients.md#mobile-clients) et à utiliser l'application mobile : [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > Si vous êtes situé en Chine, rendez-vous ici pour [Obtenir Teams pour Android en Chine](get-teams-android-in-china.md)

4.  Répartissez le personnel de votre [assistance](troubleshoot-installation.md) pour gérer les questions des utilisateurs.


## <a name="communications"></a>Communications

Utilisez Teams pour rester en contact avec vos employés :
- Modèle d'application pour des[équipes au niveau de l'organisation](create-an-org-wide-team.md) et le [Communicateur de l'entreprise](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator)
    
- Envoyez des informations sur les stratégies de sécurité, la santé et le travail à domicile au sein de votre organisation.
    
- Utiliser les [Événements en direct](teams-live-events/what-are-teams-live-events.md) pour la sensibilisation et les réunions à l’échelle de l’entreprise. Pour des réunions comprenant plus de 250 participants, organisez un événement en direct. 

## <a name="personal-considerations"></a>Considérations personnelles

Voici quelques conseils pour travailler avec succès à partir du domicile :

- Disposez d’un espace de travail physique bien défini avec un bon éclairage et une ergonomie parfaite.

- Définissez des limites claires en matière d'horaire de travail et d'engagement, et utilisez les [état de présence](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) de Teams pour indiquer que vous êtes en déplacement.

- « Commutez » vers et à partir de votre bureau professionnel à domicile de façon délibérée. Ne transformez pas de travail à distance en domicile-égal-travail.

- Levez-vous et faites régulièrement des pauses. Faites une promenade, des exercices d'étirement, prenez une tasse de café.

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>Problème connu : composition des numéros de conférence dans Skype Entreprise ou Teams

Voici la synthèse de la publication du centre de Messages du 7 février 2020 (MC203397) :

Microsoft est conscient des problèmes rencontrés par des utilisateurs dans la région de la Chine lors de la numérotation des numéros de conférence Skype Entreprise ou Teams. Dans la plupart des cas, ces problèmes ne sont pas liés aux systèmes sous notre contrôle. Le problème est souvent lié aux opérateurs mobiles et téléphoniques locaux. 

Si vous rencontrez des problèmes de conférence audio, nous vous recommandons de procéder comme suit :

- Invitez l’appelant ou l’organisateur de la réunion à appeler votre numéro PSTN ou numéro de téléphone portable
- Participez à l’appel ou à la réunion à partir de votre ordinateur de bureau ou de clients mobiles en utilisant VoIP

Si vous devez enregistrer un ticket de support, veuillez indiquer ce qui suit :
    
- Heure exacte de l’appel
- Numéro de pont de conférence composé
- Réseau téléphonique de l'appelant
- Numéro de téléphone de l'appelant
