---
title: Planifier un standard automatique Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Vue d’ensemble de l’utilisation d’un standard automatique Cloud avec Skype entreprise Server 2019
ms.openlocfilehash: 2cb4c54e4c70e9187e44c5de3cb70fac85be30a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150475"
---
# <a name="plan-cloud-auto-attendants"></a>Planifier les standards automatiques Cloud

Le standard automatique utilisé avec la messagerie unifiée Exchange (Exchange Server 2013 ou Exchange Server 2016) n’est plus disponible dans Exchange Server 2019 ou Exchange Online. Si votre implémentation de Skype entreprise Server 2019 s’intègre à l’une de ces versions d’Exchange, vous devez utiliser les fonctionnalités vocales Cloud en ligne associées au système téléphonique. Reportez-vous à la rubrique [plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md) pour plus d’informations sur le transfert des services de messagerie unifiée Exchange hébergés sur exchange Server 2013 et 2016 vers le Cloud.

Cela signifie, par essence, que vous disposez d’une implémentation hybride de Skype entreprise Server 2019 si vous souhaitez utiliser des fonctionnalités de messagerie unifiée comme les standards automatiques. Pour plus d’informations [, voir Configurer la connectivité hybride entre Skype entreprise Server et Office 365](configure-hybrid-connectivity.md) .

Un standard automatique est un service Cloud qui accepte les appels des clients et émet des messages d’accueil, fournit des options de menu et interagit avec les appelants à l’aide de la voix ou de la numérotation pour acheminer les appels vers la destination appropriée. Chaque standard automatique est affecté à un **compte de ressource** (reportez-vous à la rubrique[Configure Resource Accounts](configure-onprem-ra.md)) sur votre système Skype entreprise Server 2019 qui sera directement lié à un standard automatique dans le centre d’administration Microsoft Teams. Voir [qu’est-ce que les standards automatiques Cloud ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) pour plus d’informations sur les standards automatiques et sur les options et les fonctionnalités disponibles pour les standards automatiques.

> [!NOTE]
> Vous pouvez affecter plusieurs numéros de service Microsoft ou des numéros hybrides à un standard automatique.

Un appel entrant vers un standard automatique Cloud peut prendre plusieurs chemins, comme illustré ci-dessous :

![Diagramme pour les standards automatiques](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype entreprise Server 2019
2. Via un [contrôleur de frontière de session](/MicrosoftTeams/direct-routing-border-controllers.md) et un [routage direct](/MicrosoftTeams/direct-routing-plan.md)
3. Via un numéro hébergé en ligne dans Office 365.

Voir également :

- [Configurer un standard automatique dans le cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Réponse et routage automatique d’appels entrants](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Configuration requise

La configuration requise suivante suppose que vous ayez déjà déployé Skype entreprise Server 2019 dans une topologie prise en charge.  Vos besoins dépendent de votre scénario :

- Si vous utilisez déjà la messagerie unifiée Exchange en ligne ou en local et que vous effectuez une mise à niveau vers Skype entreprise 2019, vous devrez capturer la structure de vos standards automatiques et les recréer dans le Cloud à l’aide de standards automatiques Cloud. Pour plus d’informations, consultez la rubrique [migration d’un standard automatique de messagerie unifiée Exchange ou d’une file d’attente d’appels vers un système téléphonique](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Pour une nouvelle configuration de standards automatiques Cloud, suivez les étapes décrites dans [Configure Resource Accounts](configure-onprem-ra.md).

Outre la configuration requise ci-dessus, les conditions suivantes doivent être configurées pour se connecter au service de standard automatique Cloud Microsoft :

- Connectivité hybride. Si vous avez déjà déployé Skype entreprise Server et que vous souhaitez activer le standard automatique Cloud pour vos utilisateurs sur site, vous devez vous assurer que la connectivité hybride est configurée entre votre environnement local et en ligne. Il s’agit parfois d’une configuration de domaine fractionné.

   Pour plus d’informations, voir [planifier une connectivité hybride entre Skype entreprise Server et office 365](plan-hybrid-connectivity.md) et [configurer la connectivité hybride entre Skype entreprise server et Office 365](configure-hybrid-connectivity.md).

- Si vous attribuez un numéro de téléphone à votre standard automatique, vous aurez besoin d’une licence [Office 365 entreprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) .
- Créez un [compte de ressource](/MicrosoftTeams/manage-resource-accounts.md) en ligne ou un [compte de ressource](configure-onprem-ra.md)local pour chaque standard automatique et attribuez les numéros de téléphone et les licences. 

## <a name="migration-and-interoperability"></a>Migration et interopérabilité

Si vous envisagez de déployer Skype entreprise Server 2019 et/ou Exchange Server 2019, vous devez planifier soigneusement votre migration afin de garantir la prise en charge continue des standards automatiques. Gardez les éléments suivants à l’esprit :

- Exchange Server 2019 ne fournit plus la fonctionnalité de messagerie unifiée Exchange
- La messagerie unifiée Exchange est en mode de déclassement
- Skype entreprise Server 2019 ne s’intègre plus à la messagerie unifiée Exchange Online

Les standards automatiques Cloud peuvent être configurés avec Skype entreprise Server 2019, 2015 et 2013.

Microsoft recommande les chemins de migration suivants :

- Si vous effectuez une mise à niveau vers Skype entreprise Server 2019, vous pouvez utiliser la messagerie unifiée Exchange dans Exchange Server 2013 ou 2016, mais vous devez effectuer une mise à niveau vers le standard automatique Cloud si vous utilisez Exchange Server 2019.

- Si vous effectuez une mise à niveau vers Exchange Server 2019 et que vous utilisez des versions précédentes de la messagerie UNIFIÉe Exchange Server pour la messagerie vocale Skype entreprise Server, Microsoft vous recommande d’effectuer une mise à niveau vers Skype entreprise Server 2019 avant la mise à niveau de la boîte aux lettres.  Dans le cas contraire, les fonctionnalités de messagerie vocale seront perdues.

Pour plus d’informations sur la planification de la migration, reportez-vous à la rubrique [plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migration d’un système de standard automatique de messagerie unifiée Exchange précédemment implémenté

Actuellement, nous ne prenons pas en charge la migration automatisée vers le Cloud d’un système de standard automatique de messagerie unifiée créé dans Exchange 2013 ou 2016. Pour recréer manuellement un système de standard automatique, vous devez :

1. Utilisez les commandes PowerShell d’administration Exchange pour examiner la structure de l’ancien système de standard automatique, y compris les standards automatiques imbriqués et les files d’attente d’appels.  
2. Créez des copies de scripts de synthèse vocale ou de messages enregistrés associés à chaque nœud de standard automatique de messagerie unifiée.
3. Créez des points de terminaison de site pour chaque nœud de standard automatique, y compris en affectant des numéros de téléphone de test et des licences aux objets. Notez que vous pouvez désormais attribuer des numéros de téléphone locaux aux licences utilisées par les services en ligne, tels que le système téléphonique.
4. Implémentez un nouveau service de standard automatique Cloud avec Skype entreprise Online et le système téléphonique. Voir [Configure Resource Accounts](configure-onprem-ra.md) for Implementation Details. Au fur et à mesure, téléchargez les scripts de synthèse vocale ou les messages enregistrés associés à chaque nœud de standard automatique de messagerie unifiée.
5. Testez la fonctionnalité du standard automatique Cloud.
6. Réaffectez le numéro de téléphone affecté à l’ancien standard automatique de messagerie unifiée Exchange au standard automatique de Cloud principal nouvellement créé.

Pour plus d’informations sur ces étapes, voir [migration d’un standard automatique de messagerie unifiée Exchange ou d’une file d’attente d’appels vers le système téléphonique](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) .

## <a name="additional-planning-resources"></a>Ressources de planification supplémentaires

Le didacticiel intitulé [petite entreprise-configurer un standard automatique](/microsoftteams/tutorial-org-aa) passe par le processus de collecte d’informations sur les besoins des utilisateurs, de la planification d’une structure de standards automatiques et d’utilisateurs (et éventuellement d’appels de files d’attente), de l’écriture des invites de menu et de l’implémentation du plan dans le centre d’administration Teams. Passez en revue le didacticiel et utilisez les exercices pratiques pour créer votre plan.

Lorsque vous disposez d’une structure solide qui répond à vos besoins et d’un script qui guide les clients de manière efficace, passez à la [Configuration des comptes de ressources](configure-onprem-ra.md).

> [!CAUTION]
> Comme mentionné dans [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), le transfert des standards automatiques de messagerie unifiée Exchange créés dans le serveur 2015 vers les serveurs exécutant le serveur 2019 est déconseillé. Pour le moment, vous devez les conserver dans un pool Skype entreprise Server 2015 en cours d’exécution en mode coexistence.

## <a name="see-also"></a>Voir aussi

[Planification de la migration de Skype entreprise Server et d’Exchange Server](plan-um-migration.md)

[Configurer des comptes de ressources](configure-onprem-ra.md)

[Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Qu’est-ce que les standards automatiques Cloud ?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurer un standard automatique dans le cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Messagerie unifiée Exchange : [répondre et acheminer automatiquement les appels entrants](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planifier la connectivité hybride entre Skype Entreprise Server et Office 365](plan-hybrid-connectivity.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Office 365](configure-hybrid-connectivity.md).

[KB4480742 : les appels à l’accès abonné ou au standard automatique échouent avec l’erreur Fast Busy et « 500 Server Internal » après avoir déplacé les objets contact vers Skype entreprise Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
