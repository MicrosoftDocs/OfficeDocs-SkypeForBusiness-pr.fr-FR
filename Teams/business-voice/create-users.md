---
title: Créer des utilisateurs Microsoft 365, ajouter des licences Business Voice et attribuer des numéros de téléphone
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: high
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33367a75eef98a847edfe6ce985f952719bfcf4c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605963"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a>Créez et octroyer des licences à des utilisateurs et attribuez-leur un numéro de téléphone

Pour utiliser :::no-loc text="Microsoft 365 Business Voice":::, vous avez besoin d’un compte :::no-loc text="Microsoft 365"::: possédant une licence :::no-loc text="Microsoft 365 Business Voice":::. Une fois que vous avez un compte et une licence, vous pouvez lui affecter un numéro de téléphone.

## <a name="create-and-license-users"></a>Créer des utilisateurs et leur octroyer une licence

Suivez les étapes décrites dans [Ajouter des utilisateurs individuellement ou en bloc](/microsoft-365/admin/add-users/add-users) et [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Dans le volet **Attribuer des licences de produits**, sélectionnez **:::no-loc text="Microsoft 365 Business Voice":::**.

## <a name="assign-phone-numbers-to-users"></a>Attribuer des numéros de téléphone aux utilisateurs

Après avoir créé des utilisateurs et leur avoir attribué une licence :::no-loc text="Microsoft 365 Business Voice":::, vous pouvez leur attribuer un numéro de téléphone. Vous devez avoir un numéro de téléphone non attribué pour chaque utilisateur devant passer ou recevoir des appels vers ou à partir de numéros de téléphone externes. Si vous n’avez pas assez de numéros de téléphone non attribués, consultez [Demander d’autres numéros de téléphone](#get-more-phone-numbers), plus loin dans cet article.

1. Accédez à https://admin.teams.microsoft.com.
2. Entrez un nom et une description pour la demande de numéro de téléphone.
3. Sélectionnez **Voice** > **Numéros de téléphone**.
4. Choisissez un numéro de téléphone que vous voulez attribuer à un utilisateur, puis sélectionnez **Modifier**.
5. Dans le panneau **Modifier**, entrez le nom de l’utilisateur auquel attribuer le numéro dans **Attribué à**. Puis sélectionnez **Attribuer**.
6. Pour l'**Emplacement de secours**, entrez l’emplacement où se trouve l’utilisateur, puis sélectionnez **Appliquer**

## <a name="get-more-phone-numbers"></a>Demander d’autres numéros de téléphone

Si vous n’avez pas assez de numéros de téléphone disponibles à attribuer aux nouveaux utilisateurs, vous pouvez demander des numéros supplémentaires. La mise à disposition des numéros à transférer peut prendre jusqu’à 24 heures.

1. Accédez à https://admin.teams.microsoft.com.
2. Entrez un nom et une description pour la demande de numéro de téléphone.
3. Sélectionnez **Voice** > **Numéros de téléphone** > **Voice**.
4. Sélectionnez le pays ou la région du numéro de téléphone.
5. Pour le **Type de numéro**, sélectionnez **Utilisateur (abonné)**.
6. Pour l'**Emplacement**, recherchez l’emplacement de l’utilisateur, puis sélectionnez-le. Vous pouvez également choisir d'**Ajouter un emplacement**.
7. Choisissez un indicatif régional, entrez le nombre de numéros de téléphone nécessaires, puis sélectionnez **Suivant**.
8. Patientez jusqu’à ce que les numéros de téléphone soient réservés, puis affichez les numéros reçus. Si tout semble correct, sélectionnez **passer la commande** puis **terminer la**.