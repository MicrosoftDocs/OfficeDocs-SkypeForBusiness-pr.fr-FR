---
title: Configurer la licence de téléphone de partie commune pour Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer des téléphones en zone commune pour les salles d’attente, les zones de réception et les salles de conférence '
ms.openlocfilehash: 74806d3dfc66c27c144d6c3a4e1ddd5c6c7e7c60
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204859"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurer la licence de téléphone de partie commune pour Microsoft Teams

Un téléphone en zone commune est généralement placé dans une zone comme une salle d’attente ou une autre zone qui est disponible à plusieurs personnes pour émettre un appel ; par exemple, une réception zone, salle d’attente ou une conférence téléphonique. Téléphones de partie commune sont configurés en tant que périphériques plutôt que des utilisateurs et peuvent vous connecter automatiquement à un réseau.

Dans les étapes suivantes, nous allons vous aider à configurer un compte de système téléphonique déployer les téléphones en zone commune pour votre organisation. Pour une salle de réunion plus complète optimal, y compris les services d’audioconférence, envisager d’acquérir la licence de salle de réunion dédiée à une réunion périphérique. 

Premières choses que vous devez faire est achat une licence de téléphone de zone commune (CAP) et assurez-vous que vous disposez d’un téléphone certifié. Pour rechercher et en savoir plus sur les téléphones certifiés, accédez aux [périphériques équipes Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

1. Dans le centre d’administration Office 365, accédez à la **facturation** > **services d’achat** , puis développez **autres plans**.

    ![Capture d’écran indiquant la vignette de téléphone en zone commune](media/set-up-common-area-phone-image1.png)

2. Sélectionnez le **téléphone en zone commune** > **Acheter maintenant**.

3. Sur la page de **validation** , cliquez sur **Acheter maintenant**.

4. **Les abonnements de module complémentaire** , puis cliquez sur pour acheter un Plan de l’appel. Choisissez **l’intérieur de l’appel de Plan** ou **appel nationale et International planifier**.

> [!NOTE]
> Vous n’avez pas besoin d’une licence de Système téléphonique. Il est inclus dans la licence Téléphone de zone commune.

Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences

1. Dans le centre d’administration Office 365, accédez aux **utilisateurs** > **utilisateurs actifs** > **Ajouter un utilisateur**.

2. Entrez un nom d’utilisateur comme « Main » pour le prénom et le « Réception » pour le nom du deuxième.

3. Entrez un nom d’affichage si elle n’est pas générer automatiquement comme « Réception principal. »

4. Entrez un nom d’utilisateur comme « MainReception » ou « Mainlobby ».

5. Pour les téléphones de partie commune, vous souhaitez définir un mot de passe manuellement ou ont le même mot de passe pour tous vos téléphones en zone commune. En outre, pensez à la case à cocher **faire de cet utilisateur de modifier leur mot de passe lorsqu’ils se connectent tout d’abord** .

6. Attribuer des licences à l’utilisateur. Sur la même page, cliquez pour développer **Licences produit**. Activer le téléphone en zone commune et choisissez un **Intérieur appelant planifier** ou un **national et International appelant planifier**. 

    ![Capture d’écran montrant affectation](media/set-up-common-area-phone-image2.png)

Pour plus d’informations, voir [Ajouter un utilisateur](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

Utilisez le Skype entreprise centre d’administration pour affecter un numéro à l’utilisateur.

1. Dans le centre d’administration Microsoft 365, sélectionnez **centre Admin** > **& équipes Skype** > **portail hérité**.

2. Dans Skype entreprise centre d’administration, sélectionnez **voix** > **numéros de téléphone**.

3.  Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.

4. Dans la page **affecter** , dans la boîte vocale de l’utilisateur, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez l’utilisateur dans la liste déroulante **Sélectionner un utilisateur de voix** .

5. Pendant que vous êtes là, vous devrez ajouter une adresse d’urgence. Choisissez **Rechercher par ville**, **recherche par description**ou **Rechercher par emplacement** dans la liste déroulante, puis entrez la ville, description ou l’emplacement dans la zone de texte. Une fois que vous recherchez, regardez sous **Sélectionnez une adresse d’urgence** à choisir celle de droite pour vous.

6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

   ![Capture d’écran montrant affectation](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Les utilisateurs seront affichent uniquement s’ils disposent d’une licence de système téléphonique appliquée. Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.

Pour plus d’informations, voir [mise en route des numéros de téléphone pour vos utilisateurs](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Vous pouvez également effectuer votre numéro de téléphone que vous avez avec un autre transporteur et « port » ou transférez vers Office 365. Consultez [transfert des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).


