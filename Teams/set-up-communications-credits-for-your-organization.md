---
title: Configurer les crédits de communication pour votre organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 304c08568ee39f69f727d159a5599a3a3ac89ed4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779741"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurer les crédits de communication pour votre organisation

Vous devez configurer les crédits de communications si vous souhaitez utiliser des numéros gratuits avec Skype pour Business et Teams Microsoft. Par ailleurs, nous vous conseillons de configurer des crédits de communication pour vos forfaits d’appels (nationaux ou internationaux) et les utilisateurs de l’audioconférence qui ont besoin d’être en mesure de passer des appels vers **n’importe quelle destination**. De nombreux pays ou régions sont inclus, mais certaines destinations peuvent ne pas être incluses dans les abonnements de votre plan d’appel ou de votre audioconférence. Si vous ne configurez pas la facturation et attribuez une licence de **crédit** à vos utilisateurs et que vous avez des minutes pour votre organisation (en fonction de votre forfait d’appel ou de votre plan de visioconférence dans votre pays/région), les utilisateurs ne seront pas en mesure de passer des appels ou des appels sortants à partir des réunions de conférence audio. Vous pouvez obtenir plus d’informations, y compris des montants de financement recommandés, en lisant [qu’est-ce que les crédits de communication ?](what-are-communications-credits.md)
  
> [!NOTE]
> Pour connaitre le coût, [voir les tarifs ici](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Étape 1 : affecter une licence de plan d’appel ou de conférence audio à vos utilisateurs

Lorsque vous vous inscrivez, vous obtenez un certain nombre de minutes en fonction de votre pays/région. Vous pouvez voir le nombre de minutes que vous recevez pour rechercher le pays ou la [région.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) Après l’utilisation de ces minutes, les appels seront déconnectés. Pour éviter que cela ne se reproduise, vous devez configurer des crédits de communication.
  
Pour ce faire, **vous devez affecter une licence d’audioconférence ou de système téléphonique** à vos utilisateurs.
  
- Affecter une licence de **conférence audio** à vos utilisateurs. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md).
    
    Après avoir affecté cette licence, vous devez configurer l’audioconférence. Pour obtenir des instructions détaillées, reportez-vous à [essayer ou acheter l’audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Attribution d’un **système téléphonique** et d’une licence de plan d’appel **national ou national et international** à vos utilisateurs. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md).
    
    > [!NOTE]
    > Même si cela n’est pas obligatoire pour les crédits de communication, vous devez également affecter une licence de plan d' **appel national** ou **national et international** .
  
    Après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).
    
Pour plus d’informations, reportez-vous à la rubrique [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Étape 2 : configurer les crédits de communication pour votre organisation

1. Connectez-vous au nouveau centre d’administration Microsoft 365 avec votre compte professionnel ou scolaire.
    
2. Dans le volet de navigation de gauche du centre d’administration 365 de Microsoft, accédez à **facturation** > **services**. Faites défiler vers le bas, puis sélectionnez **modules complémentaires**.

3. Sélectionnez **crédits de communication**.
    
4. Sur la **page** abonnement, entrez vos informations, puis cliquez sur **suivant**:
    
   - **Ajouter des fonds** Entrez le montant que vous souhaitez ajouter à votre compte. Si vous n’activez pas la recharge automatique, une fois ces ressources épuisées, les fonctionnalités d’appel activées à l’aide de crédits de communications seront interrompues (par exemple, service gratuit entrant). Pour éviter d’avoir besoin de réapprovisionner manuellement vos crédits de communication à chaque fois que le solde atteint 0 (zéro), nous vous recommandons d’activer la fonction de recharge automatique.
    
   - **Recharge automatique** Activer la recharge automatique permet de recharger automatiquement votre compte lorsque son solde passe en dessous d'un seuil que vous avez défini.
    
     Nous vous conseillons d’utiliser le paramètre de **recharge automatique** pour éviter toute interruption de service, si les crédits de vos communications ne s’appliquent pas 0 (zéro). Vous recevrez un message électronique lors de la recharge des transactions de recharge, lorsque les transactions de recharge (par exemple, une carte de crédit expirée), et lorsque le solde de vos crédits de communication atteint 0 (zéro).
    
   - **Montant de la recharge** Entrez dans la zone **recharger avec** le montant que vous souhaitez ajouter à votre compte dès qu’il atteint le montant du déclencheur inférieur.
    
   - **Montant du déclencheur** Entrez dans la zone montant **lorsque le solde devient inférieur** à, qui sera utilisé pour *déclencher* la recharge automatique. Lorsque votre solde devient inférieur à ce montant, le montant de la recharge sera automatiquement ajouté à votre compte.

      > [!NOTE]
     > Les fonds seront appliqués uniquement aux crédits de communication au tarif publié par Microsoft lorsque les services sont utilisés. Tout fond non utilisé dans les 12 mois suivant la date d'achat expire et est perdu. 
     > 
     > La facturation mensuelle pour les crédits de communication ne sera appliquée que si le fonds adjugé a été utilisé pour savoir comment vérifier votre utilisation mensuelle, lire le [rapport d’utilisation PSTN de Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Entrez vos informations de paiement, cliquez sur **passer la commande**.
    >[!IMPORTANT]
    >Si vous êtes un client de gestion des licences en volume, vous pouvez choisir votre numéro de contrat entreprise pour le paiement. Si vous avez plusieurs numéros d’accord entreprise, vous serez en mesure de sélectionner l’accord entreprise que vous souhaitez utiliser pour le paiement. Vous aurez également une possibilité de spécifier un numéro de commande fournisseur à associer avec le numéro d’accord entreprise (le cas échéant).
    
Le volume et le débit du forfait d’appels peuvent être préoccupés pour chaque organisation. You will need to get this type of usage data from your current service provider. Les organisations qui utilisent déjà Skype entreprise Online sont déjà en mesure d’obtenir des données**Reports** > **d’utilisation dans** le centre > d' **administration Skype entreprise**.
  
Lorsque vous configurez des crédits de communication, vous devez examiner l’utilisation des appels pour votre organisation afin de déterminer les montants dont vous avez besoin. Ces informations sont disponibles dans le rapport **Détails de l'utilisation RTC**. Ce rapport vous permet d’exporter les enregistrements de données d’appel vers Excel si vous avez besoin de stocker les données ou de créer des rapports personnalisés. Pour plus d’informations sur l’affichage de l’utilisation, consultez rapport d’utilisation de la Conférence [RTC Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Étape 3 : affecter une licence de crédits de communication aux utilisateurs

1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Dans le volet de navigation de gauche du centre d’administration Microsoft 365, **accédez à** > utilisateurs**actifs**, puis sélectionnez un ou des utilisateurs dans la liste.
    
3. Sélectionnez **licences et applications**.
    
4. Activez/désactivez l’option **crédits de communication** **pour affecter** cette licence, puis sélectionnez **Enregistrer**.
    
    > [!NOTE]
    > Même si certains de vos utilisateurs sont affectés à une licence **entreprise E5** , il est recommandé d’effectuer cette opération.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Vous souhaitez en savoir plus sur les offres et les tarifs ?

Vous pouvez consulter les offres et les tarifs en visitant l’un des liens suivants :
  
- [Forfaits d’appel](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Plans de conférences audio](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Plans de système téléphonique](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Vous pouvez également consulter des informations en vous [connectant au centre d’administration 365 Microsoft](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) et en accédant à **facturation** > **abonnements** > **Ajouter des abonnements**.
  
Pour afficher le tableau de la licence ou des licences dont vous avez besoin pour chaque fonctionnalité, reportez-vous à la rubrique [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Voir aussi

- [Configurer Skype entreprise Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configuration de la messagerie vocale Cloud : Aide pour l'administrateur](set-up-phone-system-voicemail.md)
    
- [Configurer des Forfaits d’appels](set-up-calling-plans.md) et [Forfaits d’appels pour Office 365](calling-plans-for-office-365.md)
    
- [Ajouter des fonds et gérer les Crédits de Communications](add-funds-and-manage-communications-credits.md)
    
  
 
