---
title: Configurer la licence zone Téléphone commun
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Découvrez comment configurer les téléphones communs pour les centres d’accueil, les zones de réception et les salles de conférence '
ms.openlocfilehash: ad38f753b109aefd0e7628efe3e61472e7149597
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733753"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurer la licence de téléphone de partie commune pour Microsoft Teams
> [!NOTE]
> Les téléphones de la zone commune ne supportent pas la messagerie vocale.

Un téléphone commun est généralement placé dans une zone telle qu’une salle d’accueil ou une autre zone accessible à de nombreuses personnes pour appeler. par exemple, une zone de réception, une salle d’accueil ou un téléphone de conférence. Les téléphones de zone commune sont inscrits avec des comptes liés à une licence zone Téléphone commun. La stratégie TeamsIPPhone doit également être définie de manière appropriée pour que le téléphone offre une expérience utilisateur commune.

Dans les étapes ci-dessous, nous allons vous aider à configurer un compte pour les utilisateurs Système téléphonique déployer des téléphones en zone commune pour votre organisation. Pour une expérience de salle de réunion plus complète, y compris les audioconférences, envisagez d’acheter la licence de salle Salle de réunion dédiée avec un appareil de salle de réunion. 

Tout d’abord, vous devez acheter une licence zone Téléphone (CAP) et vous assurer que vous avez un téléphone certifié. Pour rechercher et en savoir plus sur les téléphones certifiés, voir [Microsoft Teams appareils certifiés.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

1. Dans le Centre d’administration Microsoft 365, allez aux services **d’achat** de  >   facturation, puis développez **Autres plans.**

    ![Capture d’écran montrant la vignette Téléphone commun.](media/set-up-common-area-phone-image1.png)

2. Sélectionnez **Zone commune Téléphone** acheter  >  **maintenant.**

3. Dans la page De achat, cliquez sur **Acheter maintenant.**

4. Développez **les abonnements au** module extension, puis cliquez pour acheter un forfait d’appels. Choisissez **l’un des plans d’appels nationaux** ou **nationaux et internationaux.**

> [!NOTE]
> Si vous utilisez un Téléphone Microsoft routage direct du système, vous n’avez pas besoin d’une licence de plan d’appels.

> [!NOTE]
> Vous n’avez pas besoin d’ajouter Système téléphonique licence. Il est inclus dans la licence Téléphone de zone commune.

Pour plus d’informations sur les licences, voir [Microsoft Teams licences de module complémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

La licence Domaine commun Téléphone prend en charge : 


| &nbsp;  |  Téléphone de zone commune  |
|---------|---------|
|Skype Entreprise |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Système téléphonique |    &#x2714; |
|Audioconférence |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilité mondiale |       &#x2718; &sup2;  |
|Disponibilité des canaux |    EA, EAS, CSP, Cloud de la communauté du secteur public, EES, Web Direct  |
|      |         |

&sup1; Les téléphones de la zone commune peuvent participer à des audioconférences via un numéro d’accès fourni par l’organisateur de la réunion

&sup2; Non disponible dans des nuages souverains  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences

1. Dans le Centre d’administration Microsoft 365, voir **Utilisateurs**  >  **actifs**  >  **ajouter un utilisateur.**

2. Entrez un nom d’utilisateur tel que « Principal » pour le prénom et « Réception » pour le deuxième nom.

3. Entrez un nom d’affichage s’il ne prend pas en main un nom tel que « Réception principale ».

4. Entrez un nom d’utilisateur tel que « MainReception » ou « Mainlobby ».

5. Pour les téléphones de zone commune, vous pouvez définir un mot de passe manuellement ou avoir le même mot de passe pour tous vos téléphones de zone commune. De plus, vous pouvez être plus à même d’effacer la case à cocher Faire en sorte que l’utilisateur change de mot de passe lors de **sa** première inscription.

6. Attribuez les licences à l’utilisateur. Sur la même page, cliquez pour développer **Licences produit**. Vous pouvez activer la zone Téléphone et choisir un **plan** d’appels nationaux ou un **plan d’appels nationaux et internationaux.** 

    ![Capture d’écran montrant l’attribution de licences avec les options plan d’appels nationaux et nationaux et internationaux mises en évidence.](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Si vous utilisez un Téléphone Microsoft routage direct du système, vous n’avez pas besoin d’affecter une licence de plan d’appels.

Pour plus d’informations, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

Utilisez le Teams centre d’administration pour attribuer un numéro à l’utilisateur.

1. Dans la Teams d’administration, sélectionnez **Numéros**  >  **Téléphone voix.**

3.    Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.

4. Dans la **page** Affecter, dans la zone Utilisateur vocal, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez-le dans la liste de sélection d’un utilisateur vocal. 

5. Vous devez ensuite ajouter une adresse de secours. Sélectionnez Rechercher **par** ville,  Rechercher par **description** ou Rechercher par emplacement à partir de la liste drop-down, puis entrez la ville, la description ou le lieu dans la zone de texte. Une fois que vous avez recherché, regardez sous **Sélectionner l’adresse** d’urgence pour choisir celle qui vous est la plus proche.

6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

   ![La capture d’écran montre un exemple d’attribution de licence utilisateur.](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Les utilisateurs ne s’afficheront que s’ils ont Système téléphonique licence utilisateur. Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.

Pour plus d’informations, voir [Obtention de numéros de téléphone pour vos utilisateurs.](getting-phone-numbers-for-your-users.md)

Vous pouvez également prendre votre numéro de téléphone que vous avez avec un autre opérateur et le transférer vers un opérateur Microsoft 365 ou un Office 365. Voir [Transférer des numéros de téléphone vers Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
