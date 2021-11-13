---
title: Meilleures pratiques de sécurité Teams pour une messagerie plus sûre
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Référence rapide sur l’utilisation sécurisée de Teams, cet article sert d’introduction aux meilleures pratiques générales en matière de sécurité et aux conseils pour former les utilisateurs à la messagerie sécurisée.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909679"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Meilleures pratiques de sécurité pour Microsoft Teams

La collaboration via la messagerie instantanée et la vidéoconférence a permis à de nombreux secteurs d’activité et établissements scolaires de poursuivre leur travail pendant la pandémie. Toutefois, la collaboration en ligne en temps réel à une telle échelle est également associée à des *risques* qui doivent être traités. Sinon, les acteurs malveillants tirent parti de ce changement dans le travail et la vie avec les campagnes d’**hameçonnage** et de **courrier indésirable**. La liste de référence numérotée de cet article sert de base pour la sécurité générale lors de l’utilisation de Teams pour envoyer des messages à d’autres personnes, et fournit des conseils de formation pour les personnes qui débutent dans Teams ou pour toute sécurité de messagerie instantanée.

Les mêmes risques d’hameçonnage qui existent dans le courrier électronique existent dans les applications de messagerie instantanée et de collaboration. Par conséquent, la même sensibilisation des utilisateurs et les mêmes conseils doivent être appliqués pour protéger les utilisateurs teams.

Au niveau de l’utilisateur, certaines mesures peuvent être simples et les utilisateurs doivent se sentir habilités à s’appuyer dessus. Les utilisateurs ne doivent pas cliquer pour ouvrir les liens de toute personne qu’ils ne connaissent pas ou dont ils ne peuvent pas vérifier l’identité conformément à l’article [Protection contre le hameçonnage](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44). Et pour se protéger contre les attaques externes, les administrateurs clients peuvent désactiver ou fermer l’interopérabilité de la fédération d’entreprise de Teams for Life (TFL) et Skype, en ce qui concerne [Gérer l’accès externe (fédération) Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access).

L’ensemble de fonctionnalités de collaboration Teams permet la messagerie, la collaboration de fichiers, les réunions, les tableaux blancs et de nombreuses autres opportunités de connexion. Ces fonctionnalités fonctionnent dans Teams entreprise, Teams pour la vie, Skype, Skype Entreprise, Azure Communication Services (ACS) et bien plus encore. Cela signifie également qu’il est nécessaire de vous protéger vous-même, vos pairs et vos clients dans l’ensemble de ces fonctionnalités. Là encore, chaque utilisateur doit être habilité à prendre la décision la plus sûre pour lui-même, ses pairs et ses clients.

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>Tout comme pour le courrier électronique, la sécurité en ligne doit être mise en pratique dans la messagerie Microsoft Teams

Les mesures de sécurité standard doivent être prises en compte lors de l’utilisation de Teams.

1. Soyez prudent avec les contacts et les demandes de réunion provenant de l’extérieur de votre organisation. Les inconnus peuvent être bien intentionnés. Et certains peuvent signifier secrètement des dommages.
2. Si vous ne reconnaissez pas l’expéditeur, vous pouvez vérifier son identité dans la liste d’adresses globale connue de votre entreprise et faire remonter les communications que vous ne pouvez pas vérifier à un niveau supérieur pour la gestion. En cas de doute, n’interagissez pas avec des utilisateurs inconnus et non vérifiés.
3. Si vous recevez un lien ou un fichier d’une personne inconnue, ne cliquez pas dessus. Là encore, utilisez votre meilleur choix pour vous-même et la sécurité des autres utilisateurs, ainsi que de vos clients.
4. Si une navigation par liens cliqués vous permet d’accéder à une page de liens fiables dans laquelle vous êtes bloqué, n’essayez pas de contourner cette page (il en va de même pour toute pièce jointe cliquée qui peut se terminer par une page rouge de pièces jointes sécurisées bloquante). Si vous connaissez et approuvez le site cible, signalez le problème à Microsoft et à la personne qui vous y a dirigé. Mais il existe de nombreuses raisons d’accéder à une page de blocage, et les indicateurs rouges doivent être pris en compte, plutôt que circonflexes.
5. Ne donnez jamais d’informations personnelles à des demandes non sollicitées. Il s’agit également d’un risque pour la sécurité personnelle. Des détails aussi simples que votre anniversaire peuvent être exploités par des attaquants.
6. Analysez vos liens à la recherche d’orthographe, de chiffres ajoutés ou de caractères étranges. Vous attendez peut-être un lien vers `www.litware.com/strategies/Metricsbreakout.xlsx` mais trouvez que l’adresse ressemble à `www.litwre.com`, `www.litwarecom.com` ou même `www.litwαre.com`. Si vous ne reconnaissez pas le lien, soyez suspicieux. L’adresse `www.litware.com` n’est pas identique à `www.litware2021.com`.

Il est important de maintenir votre garde et de ne pas prendre votre sécurité, et la sécurité des personnes avec qui vous travaillez à la légère, ou pour des raisons accordées. En tant qu’utilisateurs individuels, vous devez toujours vous sentir habilité à vous protéger vous-même et vos pairs et vos clients en vérifiant avant de faire confiance.

Enfin, il est également essentiel de reconnaître que tout le monde fait des erreurs. Les utilisateurs peuvent être sujets à cliquer si vous êtes pressé par exemple, ou en cas de fatigue. Les administrateurs doivent s’assurer que les ressources permettant de faire remonter les clics sur des liens problématiques et d’autres incidents de sécurité sont clairement connues des utilisateurs de leur organisation, afin que, en cas d’erreur, l’utilisateur ait des difficultés et que d’autres mesures de sécurité puissent être prises.

> [!TIP]
> Vérifiez la carte de profil d’un contact dont vous n’êtes pas sûr, en particulier si l’e-mail est externe à votre entreprise (par exemple, un compte se terminant par *@litware.com* si votre organisation n’est pas *Litware*). Un utilisateur peut vérifier que les personnes qu’il ne connaît pas sont des invités bienvenus à une réunion en vérifiant la carte de profil pour **(INVITÉ)**. Les invités sont expressément invités à participer.