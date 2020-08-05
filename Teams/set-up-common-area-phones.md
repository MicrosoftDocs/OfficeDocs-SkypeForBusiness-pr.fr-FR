---
title: Configuration de la licence de téléphone commune
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Apprenez à configurer des téléphones communs pour les couloirs, les zones de réception et les salles de conférence. '
ms.openlocfilehash: d9d77765451f98028f808028822ec42e6e51fdc7
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552302"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurer la licence de téléphone de partie commune pour Microsoft Teams
> [!NOTE]
> Les téléphones ordinaires ne prennent pas en charge la messagerie vocale.

En règle générale, un téléphone commun est placé dans une zone telle que la salle d’attente ou une autre zone qui est disponible pour de nombreux utilisateurs pour passer un appel ; par exemple, une zone de réception, une salle d’attente ou un téléphone de conférence. Les téléphones de surface commune sont connectés avec des comptes liés à une licence de téléphone commune. La stratégie TeamsIPPhone doit également être correctement définie pour que le téléphone dispose d’une interface utilisateur commune.

Dans la procédure ci-dessous, nous allons vous aider à configurer un compte pour le système téléphonique afin de déployer des téléphones de zone commune pour votre organisation. Pour une interface de salle de réunion plus complète, y compris l’audioconférence, envisagez d’acheter une licence de salle de réunion dédiée avec un appareil de salle de réunion. 

Tout d’abord, vous devez acheter une licence de téléphone pour les zones communes et vérifier que vous disposez d’un numéro de téléphone certifié. Pour en savoir plus sur les téléphones certifiés, accédez à la zone [appareils Microsoft teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

1. Dans le centre d’administration Microsoft 365, accédez **Billing**à  >  **services d’achat** de facturation, puis développez **autres plans**.

    ![Capture d’écran montrant la vignette téléphonique de zone commune](media/set-up-common-area-phone-image1.png)

2. Sélectionnez l’option d’achat de votre **téléphone courante**  >  **Buy now**.

3. Dans la page validation, cliquez sur **acheter maintenant**.

4. Développez **abonnements de modules complémentaires** , puis cliquez sur pour acheter un plan d’appels. Choisissez le forfait d' **appels nationaux** ou les offres d' **appels nationaux et internationaux**.

> [!NOTE]
> Si vous utilisez le routage direct du système Microsoft Phone, vous n’avez pas besoin d’une licence de plan d’appel.

> [!NOTE]
> Vous n’avez pas besoin d’ajouter une licence de système téléphonique. Il est inclus dans la licence Téléphone de zone commune.

Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

La licence de téléphone commune prend en charge les éléments suivants : 


|   |  Téléphone de zone commune  |
|---------|---------|
|Skype Entreprise |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Système téléphonique |    &#x2714; |
|Audioconférence |       &#x2718; &sup1 ;  |
|Microsoft Intune |        &#x2718; &sup2 ; |
|Disponibilité dans le monde entier |    &#x2714; |
|Disponibilité du canal |    AE, EAS, CSP, GCC, EES, Web direct  |
|      |         |

&sup1 ; Les téléphones ordinaires peuvent participer à des conférences audio par le biais d’un numéro de connexion fourni par l’organisateur de la réunion.

&sup2 ; Non disponible dans les nuages souverains  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences

1. Dans le centre d’administration 365 de Microsoft, accédez à **utilisateurs**  >  **actifs utilisateurs**  >  **Ajouter un utilisateur**.

2. Entrez un nom d’utilisateur tel que « main » pour le prénom et « réception » pour le second nom.

3. Entrez un nom d’affichage s’il n’en génère pas une de la façon suivante : « réception principale ».

4. Entrez un nom d’utilisateur (par exemple, « MainReception » ou « Mainlobby »).

5. Pour les téléphones portables courants, il est possible que vous deviez définir un mot de passe manuellement ou utiliser le même mot de passe pour tous les téléphones de votre zone commune. Par ailleurs, vous pouvez penser à décocher la case **faire en sorte que l’utilisateur modifie son mot de passe lors de la première connexion** .

6. Attribuez les licences à l’utilisateur. Sur la même page, cliquez pour développer **Licences produit**. Activez le téléphone courant et sélectionnez un **plan d’appels nationaux** ou un plan d' **appels nationaux et internationaux**. 

    ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Si vous utilisez le routage direct du système Microsoft Phone, il est inutile d’affecter une licence de plan d’appel.

Pour plus d’informations, voir [attribuer des licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

Utilisez le centre d’administration teams pour attribuer un numéro à l’utilisateur.

1. Dans le centre d’administration teams **Voice**, sélectionnez  >  **numéros de téléphone**vocaux.

3.    Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.

4. Dans la page **assigner** , dans la zone utilisateur vocal, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez l’utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal** .

5. Ensuite, vous devez ajouter une adresse de secours. Sélectionnez **Rechercher par ville**, **Rechercher par Description**ou **Rechercher par emplacement** dans la liste déroulante, puis entrez la ville, la description ou l’emplacement dans la zone de texte. Lorsque vous effectuez une recherche, recherchez sous **Sélectionner une adresse de secours** pour choisir celle qui vous convient.

6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

   ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Les utilisateurs ne s’afficheront que s’ils disposent d’une licence de système téléphonique appliquée. Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.

Pour plus d’informations, reportez-vous à [la rubrique réception des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).

Vous pouvez également utiliser votre numéro de téléphone avec un autre opérateur et « port », ou le transférer sur Microsoft 365 ou Office 365. Voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
