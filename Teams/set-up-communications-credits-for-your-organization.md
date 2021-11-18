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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: a7eab97eb3a69c8fd18442a4f8f132ec02cf9671
ms.sourcegitcommit: d9778b925873648213f05e27385255ba66cf8492
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61055555"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurer les crédits de communication pour votre organisation

Vous devez configurer les crédits de communications si vous souhaitez utiliser des numéros gratuits avec Skype pour Business et Teams Microsoft. En outre, nous vous recommandons de configurer les crédits de communication pour les utilisateurs de vos forfaits d’appels (nationaux ou internationaux) et de l’audioconférence qui ont besoin de pouvoir appeler vers n’importe quelle **destination.** De nombreux pays/de nombreuses régions sont inclus, mais il est possible que certaines destinations ne soient pas incluses dans votre offre d’appels ou dans vos abonnements à l’audioconférence. Si vous ne définissez pas la facturation des crédits de communication et si vous n’affectez pas de licences crédits de communication à vos **utilisateurs** et que vous n’avez plus de minutes d’appel (selon votre plan d’appels ou d’audioconférence dans votre pays/région), ces utilisateurs ne pourront plus appeler ou sortir d’un appel sortant d’une réunion d’audioconférence. Vous pouvez obtenir plus d’informations, notamment sur les montants des fonds recommandés, en lisant l’information Sur [les crédits de communication.](what-are-communications-credits.md)
  
> [!NOTE]
> Pour connaitre le coût, [voir les tarifs ici](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Étape 1 : affecter une licence d’audioconférence ou de plan d’appel à vos utilisateurs

Lorsque vous vous inscrivez, vous obtenez un certain nombre de minutes en fonction de votre pays/région. Vous pouvez rechercher votre pays ou région dans la liste de disponibilité du pays ou de la région pour les plans d’audioconférence et d’appel pour voir le nombre de minutes que vous recevrez. [](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) Une fois ces minutes déconnectées, les appels sont déconnectés. Pour éviter cela, vous devez configurer les crédits de communication.
  
Pour ce faire, vous devez affecter une licence d’audioconférence **Système téléphonique** vos utilisateurs.
  
- Affectez **une licence d’audioconférence** à vos utilisateurs. Voir [Attribuer Microsoft Teams licences de modules add-on.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    Une fois que vous aurez attribué cette licence, vous devrez configurer l’audioconférence. Pour obtenir des instructions détaillées, voir Essayer ou acheter l’audioconférence dans Microsoft 365 [ou Office 365.](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- Affectez **Système téléphonique** et une licence De plan **d’appels** nationaux ou nationaux et internationaux à vos utilisateurs. Voir [Attribuer Microsoft Teams licences de modules add-on.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    > [!NOTE]
    > Bien que cela ne soit pas obligatoire pour les crédits de communication, vous devez également affecter une licence **Plan** d’appels nationaux ou **Plan** d’appels nationaux et internationaux.
  
    Après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions détaillées, voir [Configurer les forfaits d’appels.](set-up-calling-plans.md)
    
Pour plus d’informations, [voir Microsoft Teams licences de module complémentaire](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Étape 2 : configurer les crédits de communication pour votre organisation

1. Connectez-vous au [Centre d'administration Microsoft 365](https://portal.office.com/Adminportal) à l’grâce à votre compte scolaire ou scolaire.
    
2. Dans le navigation gauche du Centre d'administration Microsoft 365, allez à **Billing**  >  **Purchase Services.** Faites défiler vers le bas **et sélectionnez Modules add-ons.**

3. Sélectionnez **Crédits de communication.**
    
4. Sur la page **d’abonnement Crédits** de communication, remplissez vos informations, puis cliquez sur **Suivant**:
    
   - **Ajouter des fonds** Entrez le montant que vous voulez ajouter à votre compte. Si vous n’activez pas la recharge automatique, les capacités d’appel activées à l’aide des crédits de communication (par exemple, service entrant gratuit) seront interrompues une fois ces fonds épuisés. Pour éviter de devoir recharger manuellement votre solde de crédits de communication chaque fois qu’il atteint 0 (zéro), nous vous recommandons d’activer la fonctionnalité de recharge automatique.
    
   - **Recharge automatique** Activer la recharge automatique permet de recharger automatiquement votre compte lorsque son solde passe en dessous d'un seuil que vous avez défini.
    
     Nous vous recommandons d’utiliser le paramètre de **recharge** automatique pour éviter toute interruption de service au cas où votre solde de crédits de communication atteint 0 (zéro). Un courrier électronique vous est envoyé en cas de réussite des transactions de recharge, en cas d’échec des transactions de recharge (par exemple en cas de carte de crédit expirée) et lorsque le solde de vos crédits de communication atteint 0 (zéro).
    
   - **Montant de la recharge** Entrez le montant dans la **zone Recharger avec** que vous souhaitez ajouter à votre compte une fois qu’il a atteint le montant de déclenchement ci-dessous.
    
   - **Montant déclencheur** Entrez le montant dans **Lorsque le solde passe** en dessous de la zone utilisée pour déclencher la recharge automatique.  Lorsque votre solde passe en dessous de ce montant, le montant de recharge est automatiquement ajouté à votre compte.

      > [!NOTE]
     > Le crédit s’appliquera uniquement aux crédits de communication aux tarifs publiés par Microsoft lorsque les services sont utilisés. Tout fond non utilisé dans les 12 mois suivant la date d'achat expire et est perdu. 
     > 
     > Lorsque vous utilisez la fonction de recharge automatique, la facturation des crédits de communication est générée lorsque le montant du déclencheur est atteint et qu’une transaction de recharge est traitée. Les montants des crédits de communication sont utilisés d’une première manière. Pour savoir comment vérifier votre utilisation mensuelle, lisez Microsoft Teams [rapport d’utilisation PSTN.](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)
    
5. Entrez vos informations de paiement, cliquez sur **passer la commande**.
    >[!IMPORTANT]
    >Si vous êtes un client de gestion des licences en volume, vous pouvez choisir votre numéro de contrat entreprise pour le paiement. Si vous avez plusieurs numéros d’accord entreprise, vous serez en mesure de sélectionner l’accord entreprise que vous souhaitez utiliser pour le paiement. Vous aurez également une possibilité de spécifier un numéro de commande fournisseur à associer avec le numéro d’accord entreprise (le cas échéant).
    
Chaque organisation utilisera différemment le volume et les tarifs des forfaits d’appels. You will need to get this type of usage data from your current service provider. Les organisations qui utilisent déjà Skype Entreprise Online ou Microsoft Teams comme fournisseur de services peuvent obtenir des données d’utilisation en les révisant dans le rapport d’utilisation PSTN et SMS  >    >    >  **(aperçu)** du Centre d’administration Microsoft Teams Analytics &.
  
Lors de la configuration des crédits de communication, vous devrez examiner l’utilisation des appels pour votre organisation afin de déterminer les montants dont vous avez besoin. Vous pouvez obtenir des informations sur l’utilisation des appels en vous reportant au rapport d’utilisation **PSTN et SMS (prévisualisation).** Ce rapport vous permet d’exporter les enregistrements de données d’appel vers Excel si vous avez besoin de stocker les données ou de créer des rapports personnalisés. Pour découvrir comment consulter l’utilisation, lisez Microsoft Teams [rapport d’utilisation PSTN.](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Étape 3 : affecter une licence crédits de communication à des utilisateurs

1. Connectez-vous au [Centre d'administration Microsoft 365](https://portal.office.com/Adminportal) à l’grâce à votre compte scolaire ou scolaire.
    
2. Dans le navigation gauche du Centre d'administration Microsoft 365, sélectionnez Utilisateurs actifs, puis sélectionnez un utilisateur  >  dans la liste.
    
3. Sélectionnez **Licences et Applications.**
    
4. Pour attribuer cette licence, basculez les **crédits** de communication sur **Actif,** puis sélectionnez **Enregistrer.**
    
    > [!NOTE]
    > Même si certains de vos utilisateurs ont Enterprise **licence E5,** il est recommandé de le faire.

    > [!TIP]
    > Vous pouvez utiliser [PowerShell pour attribuer](/powershell/module/skype/?view=skype-ps&preserve-view=true) des licences et des applications à plusieurs utilisateurs à l’grâce d’une seule commande.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Vous souhaitez en savoir plus sur les offres et les tarifs ?

Vous pouvez consulter les plans et les tarifs en visitant l’un des liens suivants :
  
- [Forfaits d’appel](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Plans d’audioconférence](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Système téléphonique de projets](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Vous pouvez également consulter des informations en [vous Centre d'administration Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) au service de facturation Et d’ajouter   >    >  **des abonnements.**
  
Pour consulter un tableau des licences dont vous avez besoin pour chaque fonctionnalité, consultez Microsoft Teams [licences de modules add-on.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="related-topics"></a>Voir aussi

- [Configurer Skype entreprise Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configuration de la messagerie vocale Cloud : Aide pour l'administrateur](set-up-phone-system-voicemail.md)
    
- [Configurer des forfaits d’appels](set-up-calling-plans.md) [et des forfaits d’appels Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
    
- [Ajouter des fonds et gérer les Crédits de Communications](add-funds-and-manage-communications-credits.md)
    
  
