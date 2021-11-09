---
title: Qu’est-ce qu’une demande de transfert ?
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: Obtenez une vue d’ensemble des commandes de transfert et de la manière de transférer des numéros de téléphone de votre fournisseur de services vers Teams.
ms.openlocfilehash: a6ff4bffe4602eca7150a9f6c8c1b69782646e7c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833028"
---
# <a name="whats-a-port-order"></a>Qu’est-ce qu’une demande de transfert ?

Si vous êtes opérateur ou fournisseur de services téléphoniques et que vous disposezdéjà de numéros de téléphone pour vos utilisateurs ou services, vous devez créer une « demande de transfert » pour transférer ces numéros de téléphone vers Microsoft Teams. Lorsque les numéros sont portés, vous pouvez affecter ces numéros de téléphone à vos utilisateurs et à des services tels que les audioconférences (pour les ponts de conférence), les ports automatiques et les files d’attente d’appels.
  
Une fois vos numéros de téléphone Teams, Microsoft devient votre fournisseur de services et vous pouvez déconnecter votre service auprès de votre ancien opérateur ou fournisseur de services.

Examinez les informations de cet article pour vous familiariser avec le portage de numéro. Après cela, vous devriez être prêt à créer une demande de transfert et à transférer vos numéros de téléphone. Pour obtenir des instructions [détaillées, voir](transfer-phone-numbers-to-teams.md) Transférer des numéros de Teams des numéros de téléphone.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Quels pays ou régions le portage de numéro est prise en charge ?

Vous pouvez transférer des numéros de téléphone dans tous les pays ou régions pris en charge, mais la façon d’envoyer une demande de transfert dépend du pays ou de la région d’origine des numéros de téléphone. Pour obtenir la liste des pays et régions qui prendrent en charge le portage des numéros, voir Gérer les numéros [de téléphone pour votre organisation.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Actuellement, [l’Assistant Porting](transfer-phone-numbers-to-teams.md) du Centre d Microsoft Teams’administration prend en charge la obtention de numéros de téléphone pour le Royaume-Uni, les États-Unis et le Canada. Pour obtenir des numéros de téléphone pour d’autres pays et régions, vous pouvez [envoyer manuellement une demande de port.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Quels sont les numéros qui peuvent être transférés ?

 **Vous pouvez transférer**
  
En règle générale, vous pouvez transférer n’importe quel numéro de téléphone d’un fournisseur pris en charge, notamment :
  
- Numéros de téléphone fixes.

- des numéros de téléphone d’appareil mobile, tels que ceux utilisés pour les téléphones portables et les tablettes ;

    > [!NOTE]
    > Le transfert de numéros de téléphone mobile est uniquement disponible aux États-Unis et à Porto Rico.
  
- des numéros de téléphone payants ;

- des numéros de téléphone gratuits ;

    > [!NOTE]
    > Les numéro gratuits internationaux (UIFN) ne peuvent pas nous être transférés. 
  
- des numéros de téléphone de service, comme ceux utilisés pour les ponts de conférence, les standards automatiques, etc. ;

- des numéros de fax, mais ils ne peuvent pas être utilisés pour envoyer des télécopies. Ils doivent être affectés à un utilisateur.

- des numéros de téléphone VoIP provenant d'un fournisseur de téléphone, comme Vonage ou RingCentral.

- Skype Entreprise numéros de téléphone hybrides. Si vous souhaitez transférer ces numéros, envoyez-nous un e-mail à <ptn@microsoft.com> l’adresse .

  **Vous ne pouvez pas transférer :**
  
    > [!NOTE]
    > Pour le moment, vous ne pouvez pas transférer de numéros de téléphone qui ne sont pas en provenance d’un pays ou d’une région pris en charge, y compris les numéros de téléphone d’un fournisseur de téléphone VoIP. Pour obtenir la liste des régions et pays pris en charge, consultez la disponibilité des pays et régions pour les plans [d’audioconférence et d’appel.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- des numéros de téléphone utilisés pour les connexions de données, comme les lignes DSL ou les connexions Internet haut débit ;

- des numéros de téléphone dédiés à la télécopie.

    Si vous avez des numéros de téléphone dédiés  existants qui sont utilisés pour la télécopie, vous pouvez les transférer vers Teams mais vos services de télécopie ne continueront pas à fonctionner comme prévu. Les services de télécopie ne sont pas disponibles pour Teams clients, même si vous avez des licences pour Système téléphonique, forfait d’appels nationaux ou Forfait d’appels internationaux.

    Si vous portez le numéro de téléphone vers Teams, vous pouvez affecter ce numéro de téléphone à un utilisateur de votre organisation au lieu de l’utiliser pour la télécopie.

    > [!NOTE]
    > Pour le moment, au Royaume-Uni, le transfert de numéros non géographiques au Royaume-Uni n’est pas prise en charge, y compris les numéros partagés pour les indicatifs régionaux 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Quelles informations dois-je fournir ?

Vous devez avoir toutes les informations de compte de votre opérateur actuel. Les informations que vous entrez dans la commande de port se trouvent principalement sur la dernière facture ou sur une facture de votre fournisseur de services actuel. Vous devez également connaître la personne dont le nom est sur le compte et les numéros à porter.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Transfert complet ou transfert partiel, de quoi s'agit-il ?

Lorsque vous transférez des numéros de téléphone vers Teams, vous avez la possibilité de transférer tous vos numéros ou certains d’entre eux.
  
- **Port total** Il s’agit du transfert de tous vos numéros de téléphone à partir de votre fournisseur de services actuel vers Teams. Lorsque vous êtes invité à transférer les numéros  de téléphone, vous devez inclure le numéro de téléphone de facturation (BTN) ainsi que tous les autres numéros de téléphone sur votre compte.

    Par exemple, supposons que votre numéro de téléphone portable (BTN) *est +1 425 555 1234* et que vous voulez faire passer l’ensemble de vos 25 numéros de téléphone (+1 *425 555 1235 à 1259).* Lorsque vous suivez les instructions ci-dessous pour transférer vos numéros, vous devez saisir : **+14255551234 - +14255551259**.

- **Port partiel** Il s’agit du transfert de certains de vos numéros de téléphone entre votre fournisseur de services actuel et Teams. Lorsque vous souhaitez faire porter certains des numéros de téléphone liés au même réseau btn, **** ne devez pas inclure ** le réseau btn avec tous les autres numéros de téléphone sur votre compte.

    Par exemple, supposons que votre numéro de téléphone btn *est +1 425 555 1234* et que vous voulez uniquement porter 5 de vos 25 numéros de téléphone (+1 *425 555 1235 à 1259).* Lorsque vous suivez les instructions ci-dessous pour transférer vos numéros, vous devez saisir **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Puis-je envoyer une demande de transfert de numéro unique pour tous mes numéros à la fois ?
<a name="bkmk_type_1"> </a>

Une demande unique est nécessaire pour chaque opérateur et pour chaque type de numéro à transférer.
  
Vous devez par exemple envoyer une demande de transfert de numéro unique pour chacun des types de numéro suivants :
  
- numéros locaux , également appelés numéros d’abonné ou numéros géographiques ;

- les numéros de téléphone gratuits incluant l'un des indicatifs suivants : 800, 844, 855, 866, 877 et 888 ;

- les numéros de téléphone mobile et

- Des numéros de service qui peuvent être utilisés pour l’audioconférence dans Microsoft 365 ou Office 365.

Voici plus d’informations sur l’soumission des demandes de portage de numéros pour chacun de ces types de numéros :
  
- **Téléphone les numéros** fournis par différents opérateurs nécessitent une demande de portage unique pour les numéros avec chaque opérateur.

-  Les numéros gratuits avec des indicatifs régionaux tels que : 800, 844, 855, 866, 877 et 888 ne peuvent pas être inclus dans une demande de portage de numéro avec d’autres types de numéros. Pour ce faire, vous devez envoyer manuellement [une demande de port.](manually-submit-port-order.md) Vous ne pouvez pas les Microsoft Teams centre d’administration. Pour plus d'informations, reportez-vous à la rubrique [Gérer les numéros de téléphone de votre organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Il est important d’utiliser la lettre d’autorisation appropriée pour le pays et le type de numéros de téléphone à porter. Vous pouvez [télécharger le LOA dont vous avez besoin ici.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Les **numéros de téléphone mobile** nécessitent un code confidentiel pour autoriser le transfert. Ils doivent donc faire l'objet d'une demande de transfert de numéro distincte.

- Les demandes de transfert de **numéros de service** doivent être envoyées par eux-mêmes. Ils ne peuvent pas être envoyés avec d’autres types de numéros.

## <a name="how-long-does-it-take-to-port-numbers"></a>Combien de temps faut-il pour transférer les numéros ?
<a name="bkmk_type_1"> </a>

Une fois que vous avez terminé la demande de demande de port, son traitement peut prendre entre 7 et 14 jours. Toutefois, en fonction de votre fournisseur de services, cela peut prendre jusqu'à 30 jours. Une fois les numéros de téléphone portés, vous recevrez un e-mail de notre part pour vous faire part que vous êtes paré pour la suite.
  
Pour vérifier l’état de votre demande de port, dans le navigation gauche du Centre d’administration Microsoft Teams, cliquez sur Numéros de voice Téléphone, puis cliquez sur  >  Historique **des commandes.** Le statut de chaque commande de port est répertorié dans la **colonne** Statut.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Les numéros de téléphone des utilisateurs (abonnés) peuvent-ils être convertis en numéros de service ?
<a name="bkmk_type_1"> </a>

Oui. Il vous suffit d'envoyer une demande de service incluant le GUID de client de votre organisation et les numéros de téléphone que vous souhaitez convertir. Pour ce faire, consultez [Gérer les numéros de téléphone pour votre organisation.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Puis-je faire appel à un Teams ou à un autre opérateur ou fournisseur de services téléphoniques ?

Pour faire appel à un Teams un autre opérateur, vous devez envoyer une demande au nouvel opérateur. Vous devez également définir un code confidentiel de portage dans le Microsoft Teams d’administration.

Pour définir votre code confidentiel de portage, dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Numéros de la Téléphone vocale. Dans le coin supérieur droit de la page, sélectionnez Gérer le code confidentiel de portage, puis entrez un code confidentiel à  >  10 chiffres. 

Lorsque votre nouvel opérateur nous contactera avec la demande de portage, nous lui demanderons de fournir le code confidentiel que vous avez défini.

## <a name="common-mistakes-to-watch-out-for"></a>Erreurs courantes à surveiller
<a name="bkmk_type_1"> </a>

Il est facile de transférer un numéro. Toutefois, votre commande peut être en désordre en cas de problème avec le fournisseur de services téléphoniques, si la commande est incomplète, si des informations sont manquantes ou en cas de fautes de frappe.
  
Voici les erreurs le plus fréquentes commises lors des transferts de numéros. Épargnez-vous un appel au service client et vérifiez qu'il n'y a aucune erreur.
  
- Assurez-vous que les informations de compte que vous indiquez correspondent exactement à celles enregistrées par votre opérateur téléphonique. La non-correspondance des informations représente la cause la plus fréquente d'erreurs et de retard pour votre demande de transfert. Vérifiez les éléments suivants :

  - Le nom ou la personne autorisée à apporter des modifications au compte est correct.

  - L'adresse est correcte.

  - Le numéro de compte est correct.

  - BTN est correct.

- Assurez-vous qu’aucune fonctionnalité de contrôle d’appel avancée, par exemple la recherche d’appel ou la sonnerie distincte, n’est activée sur ces numéros de téléphone.

- Assurez-vous que vous n'avez pas adressé de nouvelles commandes de service ou de demandes de résiliation à votre fournisseur de services actuel.

- Assurez-vous que tous les numéros sont issus du même opérateur et du même compte.

- Assurez-vous que votre service est actif. Le fait de figer le compte empêche la modification des opérateurs téléphoniques sur le compte. La personne autorisée à modifier le compte doit envoyer une commande à l’opérateur actuel pour supprimer le blocage. Selon l’opérateur, ce processus peut prendre de une à trois semaines.

## <a name="related-topics"></a>Voir aussi

- [Quel est le statut de vos demandes de transfert ?](port-order-status.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](../emergency-calling-terms-and-conditions.md)
- [Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
