---
title: Rechercher des numéros de téléphone pour les utilisateurs
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment rechercher des numéros de téléphone que vous pouvez affecter à vos utilisateurs, par pays ou région et ville, et spécifiez la quantité de numéros dont vous avez besoin.
ms.openlocfilehash: 4cb30e6ef03e50c3524ccd9b5c36ae10fb8b5ab2
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681795"
---
# <a name="search-for-telephone-numbers-for-users"></a>Rechercher des numéros de téléphone pour les utilisateurs

Lorsque vous configurez des utilisateurs de votre organisation pour passer et recevoir des appels téléphoniques à l’aide de numéros de téléphone fournis par Microsoft, vous devez d’abord utiliser le **centre d’administration Microsoft Teams** et acquérir des numéros de téléphone à attribuer aux utilisateurs. Le numéro de téléphone que vous attribuez à un utilisateur est un numéro de téléphone que vous avez acquis précédemment pour votre organisation; le nombre est répertorié dans la liste déroulante lorsque vous modifiez les propriétés de l’utilisateur, puis cliquez sur **Affecter**.
  
Avant de pouvoir attribuer des numéros de téléphone fournis par Microsoft à vos utilisateurs, vous devez utiliser la page **Obtenir de nouveaux numéros** pour rechercher les numéros de téléphone disponibles. Vous pouvez effectuer une recherche par **pays (marché),****type de numéro** et **emplacement**. Vous verrez ensuite une liste d’opérateurs qui fournissent des numéros dans ce pays.

Si vous sélectionnez Microsoft comme opérateur, vous pouvez acquérir les numéros du centre d’administration Teams en entrant la quantité de numéros de téléphone dont vous aurez besoin pour vos utilisateurs. La page limite automatiquement la quantité en fonction du nombre que vous avez encore à acquérir. Si vous sélectionnez un opérateur Operator Connect, vous êtes dirigé vers la page d’accueil de l’opérateur sélectionné pour terminer l’ordre des numéros.

La façon dont vous acquérez et gérez des numéros de téléphone diffère en fonction de votre option de connectivité RTC : Forfaits d’appels Microsoft, Operator Connect ou Routage direct.

Cet article s’applique aux plans et [Operator Connect](#search-for-telephone-numbers-for-operator-connect) [d’appels Microsoft](#search-for-telephone-numbers-for-microsoft-calling-plans). Pour plus d’informations sur toutes les options, consultez [Gérer les numéros de téléphone de votre organisation](/microsoftteams/manage-phone-numbers-landing-page).

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Rechercher des numéros de téléphone pour les forfaits d’appels Microsoft

Pour rechercher des numéros de téléphone pour vos utilisateurs :
  
1. Accédez au **centre d’administration Microsoft Teams**.

2. Dans le volet de navigation gauche, sélectionnez **Voix** >  **Téléphone numéros** > **Obtenir de nouveaux numéros**.
  
    > [!IMPORTANT]
    > Pour que vous voyiez l’option **Voix** dans le volet de navigation gauche du centre d’administration Teams, vous devez d’abord acheter au moins une **licence E5 ou E3 Enterprise**, une licence **de** module complémentaire Système téléphonique ou une licence de module complémentaire **Audioconférence**.  

3. Dans la page **Sélectionner l’emplacement et la quantité** , sélectionnez un emplacement dans la liste déroulante **Pays (Marché** ).

4. Sélectionnez **Utilisateur** dans la liste déroulante **Type de nombre** .

5. Selon le pays (marché) que vous avez sélectionné, vous disposez désormais de différentes options pour vous permettre de localiser les numéros de téléphone dont vous avez besoin.  

6. Sous **Quantité**, entrez le nombre de numéros de téléphone souhaités pour votre organisation, puis cliquez sur **Suivant**. Vous avez 10 minutes pour sélectionner vos numéros de téléphone. Si vous prenez plus de 10 minutes, les numéros seront retournées au pool de numéros de téléphone.

    > [!NOTE]
    > Vous pouvez voir le nombre de numéros de téléphone disponibles (qui est basé sur le nombre de licences), répertorié en regard de **Quantity**.
  
7. Dans la page **Obtenir des numéros** , sélectionnez les numéros de téléphone souhaités, cliquez sur **Acquérir des numéros**, puis sur **Suivant**.

    > [!IMPORTANT]
    > Vous pouvez acquérir plus de numéros de téléphone que vous ne disposez de licences Microsoft. Pour déterminer le nombre de numéros de téléphone que vous pouvez acquérir, prenez votre nombre de licences de forfait d’appels Microsoft, ajoutez 10 % du nombre de licences, puis ajoutez 10, puis supprimez tout ce que vous avez déjà acquis. Par exemple, si vous disposez de 100 licences de **forfaits d’appels nationaux**, **internationaux** et/ou nationaux **et internationaux** , vous pouvez réserver 120 numéros de téléphone, en supposant que vous n’avez pas déjà acquis certains numéros de téléphone pour ces 100 utilisateurs. Pour plus d’informations, voir [Combien de numéros de téléphone pouvez-vous obtenir ?](./how-many-phone-numbers-can-you-get.md)

8. Dans la page **Confirmation** , vérifiez vos choix, puis cliquez sur **Passer une commande**.

9. Lorsque vous revenez à la page **Téléphone numéros**, sélectionnez le numéro de téléphone ou les numéros que vous souhaitez attribuer, puis cliquez sur **Modifier** pour l’affecter à un utilisateur.

## <a name="search-for-telephone-numbers-for-operator-connect"></a>Rechercher des numéros de téléphone pour Operator Connect

1. Accédez au **centre d’administration Microsoft Teams**.

2. Dans le volet de navigation gauche, sélectionnez **Voix** >  **Téléphone numéros** > **Obtenir de nouveaux numéros**.
  
    > [!IMPORTANT]
    > Pour que vous voyiez l’option **Voix** dans le volet de navigation gauche du centre d’administration Teams, vous devez d’abord acheter au moins une **licence E5 ou E3 Enterprise**, une licence **de** module complémentaire Système téléphonique ou une licence de module complémentaire **Audioconférence**.  

3. Dans la page **Sélectionner l’emplacement et la quantité** , sélectionnez un emplacement dans la liste déroulante **Pays (Marché** ).

4. Sélectionnez **Utilisateur** dans la liste déroulante **Type de nombre** .

5. Selon le pays (marché) que vous avez sélectionné, vous disposez désormais de différentes options pour vous permettre de localiser les numéros de téléphone dont vous avez besoin. Vous pouvez filtrer pour afficher uniquement les opérateurs que vous avez ajoutés en sélectionnant **Afficher mes opérateurs**.

6. Si vous avez déjà donné votre consentement à l’opérateur, vous êtes dirigé vers la page d’accueil de l’opérateur pour terminer le processus de commande.

7. Si vous n’avez pas donné votre consentement à l’opérateur, vous êtes invité à activer votre opérateur sur la page d’opérateur choisie dans le centre d’administration Teams. Pour plus d’informations, consultez [Activer un opérateur](operator-connect-configure.md#enable-an-operator).

8. Une fois votre commande terminée, votre opérateur charge les numéros de téléphone vers votre locataire et vous pouvez les affecter aux utilisateurs.  

## <a name="related-topics"></a>Sujets associés

[Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
