---
title: Créer des Microsoft 365 utilisateurs, ajouter des numéros Teams Téléphone des offres groupées d’appels et affecter des numéros de téléphone
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez comment créer des licences et les Teams Système téléphonique des utilisateurs d’une offre groupée d’appels et leur affecter des numéros de téléphone.
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb60d60a12949cbb2a0b9ac60e727cfab393de12
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053273"
---
# <a name="create-and-license-teams-phone-system-with-calling-plan-bundle-users-and-assign-them-phone-numbers"></a>Créer des licences et des Teams Système téléphonique avec les utilisateurs d’une offre groupée Forfait d’appels et leur affecter des numéros de téléphone

Pour utiliser l’Teams Système téléphonique avec l’offre groupée Forfait d’appels, vous avez besoin d’un compte Microsoft 365 qui dispose Teams Téléphone licences de forfait Forfait d’appels. Lorsque vous avez un compte et des licences, vous pouvez commencer à affecter des numéros de téléphone.

## <a name="create-and-license-users"></a>Créer des utilisateurs et leur octroyer une licence

Suivez les étapes décrites dans [Ajouter des utilisateurs individuellement ou en bloc](/microsoft-365/admin/add-users/add-users) et [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Dans le **volet Attribuer des licences de** produit, sélectionnez **Teams Téléphone’aide du plan d’appel**.

## <a name="assign-phone-numbers-to-users"></a>Attribuer des numéros de téléphone aux utilisateurs

Après avoir créé des utilisateurs et leur Teams Téléphone licence d’offre groupée Forfait d’appels, vous pouvez leur affecter des numéros de téléphone. Vous devez avoir un numéro de téléphone non attribué pour chaque utilisateur devant passer ou recevoir des appels vers ou à partir de numéros de téléphone externes. Si vous n’avez pas assez de numéros de téléphone non attribués, consultez [Demander d’autres numéros de téléphone](#get-more-phone-numbers), plus loin dans cet article.

1. Accédez au [Centre d’administration Teams](https://admin.teams.microsoft.com).
2. Entrez un nom et une description pour la demande de numéro de téléphone.
3. Sélectionnez **Voice** > **Numéros de téléphone**.
4. Choisissez un numéro de téléphone que vous voulez attribuer à un utilisateur, puis sélectionnez **Modifier**.
5. Dans le panneau **Modifier**, entrez le nom de l’utilisateur auquel attribuer le numéro dans **Attribué à**. Puis sélectionnez **Attribuer**.
6. Pour l'**Emplacement de secours**, entrez l’emplacement où se trouve l’utilisateur, puis sélectionnez **Appliquer**

## <a name="get-more-phone-numbers"></a>Demander d’autres numéros de téléphone

Si vous n’avez pas assez de numéros de téléphone disponibles à attribuer aux nouveaux utilisateurs, vous pouvez demander des numéros supplémentaires. La mise à disposition des numéros à transférer peut prendre jusqu’à 24 heures.

1. Accédez au [Centre d’administration Teams](https://admin.teams.microsoft.com).
2. Entrez un nom et une description pour la demande de numéro de téléphone.
3. Sélectionnez **Voice** > **Numéros de téléphone** > **Voice**.
4. Sélectionnez le pays ou la région du numéro de téléphone.
5. Pour le **Type de numéro**, sélectionnez **Utilisateur (abonné)**.
6. Pour l'**Emplacement**, recherchez l’emplacement de l’utilisateur, puis sélectionnez-le. Vous pouvez également choisir d'**Ajouter un emplacement**.
7. Choisissez un indicatif régional, entrez le nombre de numéros de téléphone nécessaires, puis sélectionnez **Suivant**.
8. Patientez jusqu’à ce que les numéros de téléphone soient réservés, puis affichez les numéros reçus. Si tout semble correct, sélectionnez **passer la commande** puis **terminer la**.
