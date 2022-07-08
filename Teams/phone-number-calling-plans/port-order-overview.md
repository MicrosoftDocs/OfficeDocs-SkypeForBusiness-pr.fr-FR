---
title: Qu’est-ce qu’une demande de transfert ?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Obtenez une vue d’ensemble des commandes de port et de la façon de transférer des numéros de téléphone de votre fournisseur de services vers Teams.
ms.openlocfilehash: a4062d6a5c63b590502d5afebc547bd319e2adda
ms.sourcegitcommit: 9175c6d542dd825ce965d0cb7c67264f22315202
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687830"
---
# <a name="whats-a-port-order"></a>Qu’est-ce qu’une demande de transfert ?

Si vous disposez actuellement d’un fournisseur de services téléphoniques ou d’un opérateur téléphonique et que vous disposez déjà de numéros de téléphone pour vos utilisateurs ou services, vous devez créer une « *commande de port* » pour transférer ces numéros de téléphone vers Microsoft Teams. Lorsque les numéros sont transférés, vous pouvez affecter ces numéros de téléphone à vos utilisateurs et services tels que l’audioconférence (pour les ponts de conférence), les standards automatiques et les files d’attente d’appels.
  
Une fois que vous avez transféré vos numéros de téléphone vers Teams, Microsoft devient votre fournisseur de services et vous pouvez déconnecter votre service avec votre ancien fournisseur de services ou opérateur.

Passez en revue les informations contenues dans cet article pour vous familiariser avec le portage de numéros. Après cela, vous devez être prêt à créer une commande de port et à transférer vos numéros de téléphone. Pour obtenir des instructions pas à pas, consultez [Transférer des numéros de téléphone vers Teams](transfer-phone-numbers-to-teams.md) .
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quels pays ou régions prennent en charge le portage de numéros ?

Vous pouvez porter ou transférer des numéros de téléphone dans tous les pays ou régions pris en charge, mais la façon dont vous envoyez une demande de commande de port dépend du pays ou de la région d’où proviennent les numéros de téléphone. Pour obtenir la liste des pays et régions qui prennent en charge le portage de numéros, consultez [Gérer les numéros de téléphone de votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Actuellement, [l’Assistant Portage](transfer-phone-numbers-to-teams.md) dans le Centre d’administration Microsoft Teams prend en charge l’obtention de numéros de téléphone pour le Royaume-Uni, États-Unis et le Canada. Pour obtenir des numéros de téléphone pour d’autres pays et régions, vous pouvez [soumettre manuellement une commande de port](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Quels sont les numéros qui peuvent être transférés ?

 **Vous pouvez transférer**
  
En général, vous pouvez transférer n’importe quel numéro de téléphone provenant d’un fournisseur pris en charge, notamment :
  
- Numéros de téléphone fixes.

- Numéros de téléphone d’appareil mobile tels que ceux utilisés pour le téléphone cellulaire et les tablettes.

    > [!NOTE]
    > Le transfert de numéros mobiles n’est disponible qu’au États-Unis et à Porto Rico.
  
- des numéros de téléphone payants ;

- des numéros de téléphone gratuits ;

    > [!NOTE]
    > Le numéro de téléphone libre international universel (UIFN) ne peut pas être transféré vers nous.
    > La disponibilité du portage des numéros de téléphone gratuits peut varier selon le pays et la région. Pour en savoir plus, reportez-vous aux documents spécifiques à votre pays ou région pour voir la prise en charge disponible pour le service de portage. 
  
- des numéros de téléphone de service, comme ceux utilisés pour les ponts de conférence, les standards automatiques, etc. ;

- des numéros de fax, mais ils ne peuvent pas être utilisés pour envoyer des télécopies. Ils doivent être attribués à un utilisateur.

- des numéros de téléphone VoIP provenant d'un fournisseur de téléphone, comme Vonage ou RingCentral.

- Si vous transférez des numéros de téléphone hybrides (migration depuis le routage direct ou la connexion de l’opérateur vers les forfaits d’appels), contactez [l’équipe des services de numéros](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) de téléphone, veillez à inclure une note indiquant qu’il s’agit de numéros de téléphone hybrides.

**Vous ne pouvez pas transférer :**
  
> [!NOTE]
> À ce stade, vous ne pouvez pas transférer de numéro de téléphone ou de numéros qui ne proviennent pas d’un pays ou d’une région pris en charge, y compris les numéros de téléphone d’un fournisseur de téléphone VoIP. Pour obtenir la liste des pays/régions pris en charge, consultez [la disponibilité des pays et des régions pour l’audioconférence et les forfaits d’appels](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- des numéros de téléphone utilisés pour les connexions de données, comme les lignes DSL ou les connexions Internet haut débit ;

- des numéros de téléphone dédiés à la télécopie.

    Si vous avez des numéros de téléphone dédiés existants qui sont utilisés pour la télécopie, vous  *pouvez*  transférer ces numéros vers Teams, mais vos services de télécopie ne continueront pas à fonctionner comme prévu. Les services de télécopie ne sont pas disponibles pour les clients Teams, même si vous disposez de licences pour le système téléphonique, le forfait d’appels nationaux ou le forfait d’appels internationaux.

    Si vous transférez le numéro de téléphone vers Teams, vous pouvez affecter ce numéro de téléphone à un utilisateur de votre organisation au lieu de l’utiliser pour la télécopie.

> [!NOTE]
> Actuellement, au Royaume-Uni, nous ne prenons pas en charge le transfert de numéros non géographiques au Royaume-Uni, y compris les numéros de coût partagés pour les codes régionaux 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quelles informations dois-je fournir ?

Vous devez disposer de toutes les informations de compte pour votre opérateur actuel. Les informations que vous entrez dans la commande de port se trouvent principalement sur la facture ou la facture la plus récente de votre fournisseur de services actuel. Vous devez également savoir dont le nom se trouve sur le compte et quels numéros vous voulez porter.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Transfert complet ou transfert partiel, de quoi s'agit-il ?

Lorsque vous transférez des numéros de téléphone vers Teams, vous avez la possibilité de transférer tous vos numéros ou certains d’entre eux.
  
- **Port complet** C’est à ce moment que vous transférez tous vos numéros de votre fournisseur de services actuel vers Teams. Lorsque vous êtes invité à indiquer les numéros de téléphone que vous souhaitez transférer, vous *devez inclure* le numéro de téléphone de facturation (BTN) ainsi que tous les autres numéros de téléphone de votre compte.

    Par exemple, supposons que votre BTN est  *+1 425-555-1234*  et que vous souhaitez porter tous vos 25 numéros de téléphone (*+1 425-555-1235 à 1259*). Lorsque vous suivez les instructions ci-dessous pour transférer vos numéros, vous devez saisir : **+14255551234 - +14255551259**.

- **Port partiel** C’est lorsque vous transférez uniquement certains de vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Lorsque vous souhaitez porter certains numéros de téléphone liés au même BTN, vous ne *devez pas inclure* ** le BTN ainsi que tous les autres numéros de téléphone de votre compte.

    Par exemple, supposons que votre BTN est  *+1 425-555-1234*  et que vous souhaitez porter seulement 5 de vos 25 numéros de téléphone (*+1 425-555-1235 à 1259*). Lorsque vous suivez les instructions ci-dessous pour transférer vos numéros, vous devez saisir **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Puis-je envoyer une demande de transfert de numéro unique pour tous mes numéros à la fois ?
<a name="bkmk_type_1"> </a>

Une demande unique est nécessaire pour chaque opérateur et pour chaque type de numéro à transférer.
  
Vous devez par exemple envoyer une demande de transfert de numéro unique pour chacun des types de numéro suivants :
  
- Numéros de péage locaux, également appelés numéros d’abonnés ou numéros géographiques

- les numéros de téléphone gratuits incluant l'un des indicatifs suivants : 800, 844, 855, 866, 877 et 888 ;

- les numéros de téléphone mobile et

- Numéros de service qui peuvent être utilisés pour l’audioconférence dans Microsoft 365 ou Office 365.

Voici plus d’informations sur la façon d’envoyer des demandes de portage de numéros pour chacun de ces types de nombres :
  
- **Les numéros de téléphone** fournis par différents opérateurs nécessitent une demande de portage unique pour les numéros avec chaque opérateur.

- **Les numéros gratuits** avec des codes régionaux tels que : 800, 844, 855, 866, 877 et 888 ne peuvent pas être inclus dans une demande de portage de nombres avec d’autres types de numéros. Pour porter ces numéros gratuits, vous devez [soumettre manuellement une commande de port](manually-submit-port-order.md). Vous ne pouvez pas porter ces numéros dans le Centre d’administration Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Gérer les numéros de téléphone de votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Il est important d’utiliser la lettre d’autorisation correcte (LOA) pour le pays et le type de numéros de téléphone que vous souhaitez porter. Vous pouvez [télécharger la LOA dont vous avez besoin ici](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Les **numéros de téléphone mobile** nécessitent un code confidentiel pour autoriser le transfert. Ils doivent donc faire l'objet d'une demande de transfert de numéro distincte.

- Les demandes de transfert de **numéros de service** doivent être envoyées par eux-mêmes. Ils ne peuvent pas être envoyés avec d’autres types de nombres.

## <a name="how-long-does-it-take-to-port-numbers"></a>Combien de temps faut-il pour transférer les numéros ?
<a name="bkmk_type_1"> </a>

Une fois que vous avez terminé la demande de commande de port, le traitement prend entre 7 et 14 jours. Toutefois, en fonction de votre fournisseur de services, cela peut prendre jusqu'à 30 jours. Une fois les numéros de téléphone transférés, vous recevrez un e-mail de notre part pour vous informer que vous êtes bon pour aller.
  
Pour vérifier l’état de votre commande de port, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **numéros de téléphone** **vocal** > , puis cliquez sur **Historique des commandes**. Chaque état de l’ordre de port est répertorié dans la colonne **État** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Les numéros de téléphone des utilisateurs (abonnés) peuvent-ils être convertis en numéros de service ?
<a name="bkmk_type_1"> </a>

Oui. Il vous suffit d'envoyer une demande de service incluant le GUID de client de votre organisation et les numéros de téléphone que vous souhaitez convertir. Pour ce faire, consultez [Gérer les numéros de téléphone de votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Puis-je transférer mes numéros de Teams vers un autre fournisseur de services téléphoniques ou opérateur ?

Pour transférer vos numéros de Teams vers un autre opérateur, vous devez envoyer une demande au nouveau transporteur. Vous devez également définir un code confidentiel de portage dans le Centre d’administration Microsoft Teams.

Pour définir votre code confidentiel de portage, dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **numéros de téléphone** **vocal** > , dans le coin supérieur droit de la page, sélectionnez **Gérer le code confidentiel de portage**, puis entrez un code confidentiel à 10 chiffres.

Lorsque votre nouveau transporteur nous contacte avec la demande de portage, nous lui demandons de fournir le code confidentiel que vous avez défini.

Si vous avez besoin de configurer un code confidentiel, contactez [l’équipe des services de numéro de téléphone](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>Erreurs courantes à surveiller
<a name="bkmk_type_1"> </a>

Il est facile de transférer un numéro. Toutefois, votre commande peut être désordonnée en cas de problème avec le fournisseur de services téléphoniques, si la commande est incomplète et qu’il manque des informations, ou s’il existe des fautes de frappe.
  
Voici les erreurs le plus fréquentes commises lors des transferts de numéros. Épargnez-vous un appel au service client et vérifiez qu'il n'y a aucune erreur.
  
- Assurez-vous que les informations de compte que vous indiquez correspondent exactement à celles enregistrées par votre opérateur téléphonique. La non-correspondance des informations représente la cause la plus fréquente d'erreurs et de retard pour votre demande de transfert. Vérifiez les éléments suivants :

  - Le nom ou la personne autorisée à apporter des modifications au compte est correct.

  - L'adresse est correcte.

  - Le numéro de compte est correct.

  - BTN est correct.

- Assurez-vous qu’il n’existe aucune fonctionnalité avancée de contrôle d’appel, par exemple, Call Hunt, Distinctive Ring, qui sont activées sur ces numéros de téléphone.

- Assurez-vous que vous n'avez pas adressé de nouvelles commandes de service ou de demandes de résiliation à votre fournisseur de services actuel.

- Assurez-vous que tous les numéros sont issus du même opérateur et du même compte.

- Assurez-vous que votre service est actif. Le fait de figer le compte empêche la modification des opérateurs téléphoniques sur le compte. La personne autorisée à apporter des modifications au compte doit envoyer une commande au transporteur actuel pour supprimer le gel. Ce processus peut prendre une à trois semaines en fonction du transporteur.

## <a name="related-topics"></a>Sujets associés

- [Quel est le statut de vos demandes de transfert ?](port-order-status.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](../emergency-calling-terms-and-conditions.md)
- [Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
