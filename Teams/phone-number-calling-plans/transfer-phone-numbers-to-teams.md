---
title: Transfert de numéros de téléphone dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser l’Assistant de Portage pour transférer votre numéro de téléphone de votre fournisseur de services actuel vers Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 07368b6dfd05567eac4eac66614560b6ecc9d2b4
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137864"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Transfert de numéros de téléphone dans Microsoft teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Utilisez l’Assistant de Portage dans le centre d’administration de Microsoft teams pour transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Lorsque vous transférez vos numéros de téléphone vers Teams, Microsoft deviendra votre fournisseur de services et vous facturera ces numéros de téléphone.

Avant de commencer, nous vous conseillons de passer en revue les informations relatives à [une demande](port-order-overview.md) de transfert ? Si vous disposez de numéros de service pour les ponts de conférence rendez-vous, les standards automatiques ou d’autres numéros de service, les numéros de téléphone gratuits ou dont vous avez plus de 999, vous devez transférer les numéros de téléphone de votre organisation, reportez-vous à la rubrique [gérer les numéros de téléphone de votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour télécharger les formulaires appropriés et nous les envoyer.

  > [!NOTE]
  > Les commandes de port ne sont traitées pour le transfert des numéros de téléphone qu’aux États-Unis et non aux jours fériés et week-end publics.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Création d’une demande de transfert et transfert de vos numéros de téléphone dans teams

> [!NOTE]
> Pour **l’instant, vous pouvez utiliser cet Assistant pour obtenir des numéros de téléphone pour le Royaume-Uni et le Canada**. Pour obtenir des numéros de téléphone pour d’autres pays ou régions, vous pouvez [demander manuellement une demande de](manually-submit-port-order.md)transfert. Pour obtenir le formulaire, vous devez d’abord valider manuellement une demande de transfert, puis sélectionnez votre pays ou région dans la liste déroulante [gérer les numéros de téléphone pour votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**numéros de téléphone** **vocaux** > . Cliquez sur **nombres**, puis cliquez sur **port** pour démarrer l’Assistant de Portage.
2. Passez en revue les informations de la page mise en **route** , puis, lorsque vous êtes prêt, cliquez sur **suivant**.
3. Dans la page **Sélectionner le type d’emplacement et le type de numéro** , spécifiez les informations suivantes, puis cliquez sur **suivant**:

    - **Pays ou région**: pays ou région où vous avez des numéros.
    - **Type de numéro de téléphone**: type de numéro, tel que géographique ou numéro gratuit.
    - **Numéros attribués à**: ce pour quoi les numéros sont attribués. Par exemple, des utilisateurs ou des fonctionnalités de conférence ou de voix.

4. Dans la page **Ajouter des informations** sur le compte, procédez comme suit, puis cliquez sur **suivant**.

    > [!IMPORTANT]
    > Les informations affichées sur cette page sont déterminées par le pays ou la région et le type de numéro. Pour chaque pays ou région, il existe des réglementations différentes sur les informations nécessaires aux numéros de port. Ce que vous voyez sur cette page peut être différent de celui décrit dans cet article.

    - **Détails**de la commande : 
        - **Nom**de la commande : nom de la commande
        - **Courriers électroniques de notification**: adresses de messagerie pour recevoir des notifications de bon de commande. Si vous entrez plusieurs adresses de messagerie, séparez-les par un point-virgule.
        - **Date transférée**: date de transfert émise par votre fournisseur de services actuel.
    - **Détails du numéro de téléphone**
        - **Type de port**: Si vous utilisez un port complet pour transférer tous vos numéros ou un port partiel pour transférer certains de vos numéros.
    - **Personne demandant des informations**  
        - Le nom de votre organisation et les détails de contact de la personne demandant le transfert.
    - **Détails du fournisseur actuel**
        - **Numéro de téléphone de facturation (BTN)**: votre BTN au format E. 164 (un signe +) doit précéder le numéro. Par exemple, dans le cas d’un numéro d’Amérique du Nord, utilisez + 1XXXYYYZZZZ.
        - Autres détails, y compris le nom de votre fournisseur de services actuel, le numéro de votre compte et votre adresse de service.
            
5. Dans la page **Ajouter des numéros** , cliquez sur **Sélectionner un fichier**, recherchez et sélectionnez le fichier csv contenant les numéros de téléphone que vous souhaitez transférer, puis cliquez sur **suivant**.  

    > [!NOTE]
    > Le fichier CSV ne doit comporter qu’une seule colonne avec un en-tête intitulé PhoneNumber. Chaque numéro de téléphone doit figurer sur une ligne distincte et ne peut pas contenir de chiffres ou être au format E. 164.

6. Sur la page **terminer la commande** , cliquez sur **Télécharger une lettre d’autorisation signée** pour télécharger une copie numérisée de la lettre d’autorisation signée (LOA).

    Si vous n’avez pas encore téléchargé et signé le LOA, procédez comme suit :
    
    1. Cliquez sur **Télécharger le modèle** pour télécharger le LOA pour votre pays ou région. 
    2. Imprimer le LOA.
    3. Faire en sorte que le LOA signé par la personne qui est autorisé à apporter des modifications au compte.
    4. Analysez le LOA signé, puis cliquez sur **Télécharger une lettre d’autorisation signée** pour le télécharger.

    > [!NOTE]
    > Après avoir chargé votre LOA, envoyez votre commande. Il suffit de télécharger le LOA insuffisant. Vous devez également valider la commande pour qu’elle soit traitée.

7. Passez en revue les détails de votre commande, puis cliquez sur **valider**.


## <a name="what-happens-next"></a>Que va-t-il se passer ensuite ?

Lorsque nous aurons reçu votre demande de transfert, vous recevez un courrier électronique qui confirme votre demande. Votre demande est vérifiée et mise à jour quotidiennement et vous recevez une notification d’avancement et de statut par e-mail. Si votre demande de transfert a été refusée par l’opérateur de perte, contactez le [service d’assistance RTC](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

Pour afficher l’état de votre demande de transfert, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à >**ordres de port** **vocal** > , puis cliquez sur **historique des commandes**. Chaque statut de la demande de transfert figure dans la colonne **État** . Pour en savoir plus, consultez [quel est le statut de vos demandes de transfert ?](port-order-status.md)

## <a name="related-topics"></a>Voir aussi

- [Qu’est-ce qu’une demande de transfert ?](port-order-overview.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](../emergency-calling-terms-and-conditions.md)
- [Libellé d’exclusion d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
