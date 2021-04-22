---
title: Configurer un attendant automatique pour Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Découvrez comment configurer et tester les attendants automatiques pour Microsoft Teams.
ms.openlocfilehash: 9efd30eb91e9760f800dd24935724d2a3cdd97c2
ms.sourcegitcommit: c56c87e912a4b3729c7c52d8de78fd4d24448a8d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51926050"
---
# <a name="set-up-an-auto-attendant"></a>Configurer un attendant automatique

Les employés automatiques peuvent appeler votre organisation et parcourir un système de menus pour parler au service, à la file d'attente d'appels, à une personne ou à un opérateur. Vous pouvez créer des attendants automatiques pour votre organisation à l'aide du Centre d'administration Microsoft Teams ou de PowerShell.

Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.

Les attendants automatiques peuvent diriger les appels, sur la base de l'entrée des appelants, vers l'une des destinations suivantes : <a name="call-routing-options" ></a>

- **Opérateur** (opérateur défini pour le transport automatique). La définition d'un opérateur est facultative. L'opérateur peut être défini comme n'importe quelle autre destination dans cette liste.
- **Une personne de votre organisation** qui peut recevoir des appels vocux. Il peut s'agit d'un utilisateur en ligne ou d'un utilisateur hébergé sur site utilisant Skype Entreprise Server.
- **Application vocale :** un autre service de messagerie automatique ou une file d'attente d'appels. (Choisissez le compte de ressource associé au port automatique ou à la file d'attente d'appels lorsque vous choisissez cette destination.)
- **Messagerie vocale** : boîte vocale associée à un groupe Microsoft 365 que vous spécifiez.
- **Numéro de téléphone externe -** n'importe quel numéro de téléphone. (Voir [les détails techniques du transfert externe).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Annonce (fichier audio)** : lire un fichier audio. Message d'annonce enregistré que vous téléchargez enregistré en tant qu'audio dans . WAV, . MP3 ou . Format WMA. L'enregistrement ne peut pas avoir une taille supérieure à 5 Mo. Le système lit l'annonce, puis revient au menu du transport automatique.
- **Annonce (tapée)** : taper un message. Texte que le système doit lire. Vous pouvez entrer jusqu'à 1 000 caractères. Le système lit l'annonce, puis revient au menu du transport automatique.

Vous serez invité à choisir l'une de ces options à différents stades lorsque vous configurerez un attendant automatique.

> [!NOTE]
> Lorsque vous choisissez la messagerie vocale comme destination, deux options supplémentaires sont disponibles :
> - **Transcription** (par défaut : non) : lorsqu'il est activé, le message vocal est transcrit et inclus dans le message électronique.
> - **Supprimer le message** d'accueil (par défaut : non activé) : lorsqu'il est activé, le message système standard « Veuillez laisser un message après le ton. Lorsque vous avez terminé, veuillez raccrocher ou appuyer sur le hachage pour plus d'options. » ne sera pas supprimée.

Pour configurer un attendant automatique, dans le Centre d'administration Teams, développez **Voix,** sélectionnez **Les attendants automatiques,** puis **sélectionnez Ajouter.**

## <a name="general-info"></a>Informations générales

![Capture d'écran des paramètres de attendant automatique pour les entrées de nom, d'opérateur, de fuseau horaire, de langue et de voix](media/auto-attendant-general-info-page-new.png)

1. Tapez un nom pour le attendant automatique dans la zone en haut.

2. Pour désigner un opérateur, spécifiez la destination des appels vers l'opérateur. Cette désignation est facultative (mais recommandée). Définissez **l'option** Opérateur pour permettre aux appelants de sortir des menus et de parler à une personne désignée.

3. Spécifiez le fuseau horaire de ce attendant automatique. Le fuseau horaire est utilisé pour calculer les heures d'ouverture si vous créez un flux d'appels distinct pour les [heures de travail en de suite.](#call-flow-for-after-hours)

4. Spécifiez une [langue prise en](create-a-phone-system-auto-attendant-languages.md) charge pour ce attendant automatique. Il s'agit de la langue qui sera utilisée pour les invites vocales générées par le système.

5. Choisissez si vous voulez activer les entrées vocales. Lorsqu'elle est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale. Par exemple, les appelants peuvent dire « Un » pour sélectionner l'option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner l'option de menu appelée « Ventes ».

> [!NOTE]
> Si vous choisissez une langue à l'étape 4 qui ne prend pas en charge les entrées vocales, cette option est désactivée.

6. Sélectionnez **Suivant.**

## <a name="call-flow"></a>Flux d'appels

![Capture d'écran des paramètres de message d'accueil](media/auto-attendant-call-flow-greeting-message.png)

Choisissez si vous voulez lire un message d'accueil lorsque le attendant automatique répond à un appel.

Si vous **sélectionnez Lire un fichier audio,** vous pouvez utiliser le bouton Télécharger un fichier pour télécharger un message d'accueil enregistré en tant qu'audio dans .  WAV, . MP3 ou . Format WMA. L'enregistrement ne peut pas avoir une taille supérieure à 5 Mo.

Si vous sélectionnez Taper un **message** d'accueil, le système lit le texte que vous tapez (jusqu'à 1 000 caractères) lorsque le attendant automatique répond à un appel.

![Capture d'écran des paramètres de routage des appels](media/auto-attendant-call-flow-route-call-message.png)

Choisissez la façon dont vous voulez router l'appel.

Si vous sélectionnez **Déconnecter,** le attendant automatique raccrochera.

Si vous sélectionnez **Rediriger l'appel,** vous pouvez choisir l'une des destinations de routage des appels.

Si vous sélectionnez **les options du menu** Lecture, vous pouvez choisir de lire un fichier **audio** ou de taper un **message** d'accueil, puis de choisir entre les options de menu et la recherche dans l'annuaire.

### <a name="menu-options"></a>Options de menu

![Capture d'écran des options de touches de numérotation](media/auto-attendant-call-flow-menu-options-complete.png)

Pour les options de numérotation, affectez les touches 0-9 du clavier téléphonique à l'une des destinations de routage des appels. (Touches \* (Répéter) et (Retour) sont réservés par le système et \# ne peuvent pas être réassignés.)

Les mappages de clés ne doivent pas être continus. Il est possible de créer un menu avec les touches 0, 1 et 3 mappées aux options, sans utiliser la touche numéro 2.

Nous vous recommandons de ma mappage de la touche zéro à l'opérateur si vous en avez configuré un. Si l'opérateur n'est pas réglé sur une touche quelconque, la commande vocale « Opérateur » est également désactivée.

Pour chaque option de menu, spécifiez les paramètres suivants :

- **Touche de numérotation** (clé du clavier téléphonique pour accéder à cette option). Si des entrées vocales sont disponibles, les appelants peuvent également dire ce numéro pour accéder à l'option.

- **Commande vocale** : définit la commande vocale qu'un appelant peut lui donner pour accéder à cette option, si les entrées vocales sont activées. Il peut contenir plusieurs mots tels que « Service clientèle » ou « Activités et activités ». Par exemple, l'appelant peut appuyer sur 2, dire « deux » ou dire « Ventes » pour sélectionner l'option mappée vers les deux touches. Ce texte est également restituel par sms par reconnaissance vocale pour l'invite de confirmation de service, par exemple, « Transfert de votre appel vers les ventes ».

- **Rediriger vers** (destination de routage des appels utilisée lorsque les appelants choisissent cette option). Si vous redirigez vers un service de service automatique ou une file d'attente d'appels, sélectionnez le compte de ressource qui lui est associé.

### <a name="directory-search"></a>Recherche dans l'annuaire

Si vous attribuez des touches de  numérotation aux destinations, nous vous recommandons de choisir l'aucune pour **la recherche dans l'annuaire.** Si un appelant tente de composer un nom ou une extension à l'aide de touches affectées à des destinations spécifiques, il se peut qu'ils soient acheminés de manière inattendue vers une destination avant qu'ils n'tentent de terminer la saisie du nom ou de l'extension. Nous vous recommandons de créer un attendant automatique distinct pour la recherche dans l'annuaire et de lier votre attendant automatique principal à celui-ci à l'aide d'une clé de numérotation.

Si vous n'avez pas attribué les touches de numérotation, choisissez une option pour **la recherche dans l'annuaire.**

**Numérotation par nom** : si vous activez cette option, les appelants peuvent dire le nom de l'utilisateur ou le taper sur le clavier téléphonique. Tout utilisateur en ligne ou tout utilisateur hébergé sur site utilisant Skype Entreprise Server est un utilisateur éligible et peut être trouvé avec la numérotation par nom. (Vous pouvez définir qui figure dans l'annuaire et qui n'est pas inclus dans la page de [portée de la](#dial-scope) numérotation.)

**Numérotation par extension** : si vous activez cette option, les appelants peuvent entrer en contact avec les utilisateurs de votre organisation en composant leur numéro de téléphone. Tout utilisateur en ligne ou tout utilisateur hébergé sur site utilisant Skype Entreprise Server est un utilisateur éligible et peut être trouvé avec la numérotation **par extension.** (Vous pouvez définir qui figure dans l'annuaire et qui n'est pas inclus dans la page de [portée de la](#dial-scope) numérotation.)

Les utilisateurs que vous souhaitez rendre disponibles pour la numérotation par extension doivent avoir une extension spécifiée dans [](/microsoft-365/admin/add-users/add-users) l'un des attributs de téléphones suivants définis dans Active Directory ou Azure Active Directory (voir Ajouter des utilisateurs individuellement ou en bloc pour plus d'informations).)

- OfficePhone
- Téléphone (domicile)
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

Le format requis pour entrer l'extension dans le champ Numéro de téléphone de l'utilisateur peut être l'un des formats suivants :

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- Exemple 1 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « +1555555678;ext=5678 »
- Exemple 2 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « +1555555678x5678 »
- Exemple 3 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « x5678 »

Vous pouvez définir l'extension dans le Centre [d'administration Microsoft 365](https://admin.microsoft.com/) ou le [Centre d'administration Azure Active Directory.](https://aad.portal.azure.com) Jusqu'à 12 heures peuvent être nécessaires avant que les modifications ne soient disponibles pour les attendants automatiques et les files d'attente d'appels.

> [!NOTE]
> Si vous souhaitez utiliser les fonctionnalités Numérotation **par** nom et Numérotation par **numérotation** par numérotation de poste, vous pouvez affecter une touche de numérotation sur votre postes de service automatique principal afin d'atteindre un postes de numérotation automatique activé pour la numérotation **par nom.** Dans ce attendant automatique, vous pouvez affecter la touche 1 (qui ne possède aucune lettre associée) pour atteindre le numéro par numérotation par **numérotation** automatique de poste.

Une fois que vous avez sélectionné une option **de recherche dans l'annuaire,** sélectionnez **Suivant.**

## <a name="call-flow-for-after-hours"></a>Flux d'appels pendant les heures de travail en de suite

![Capture d'écran des paramètres de jour et d'heure de fin](media/auto-attendant-business-hours.png)

Les heures d'ouverture peuvent être définies pour chaque employé de service automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures d'ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d'ouverture sont considérées comme des heures d'ouverture en de suite. Vous pouvez définir différentes options de traitement des appels entrants et des messages d'accueil pour les heures de travail en de suite.

Selon la configuration de vos files d'attente et de vos files d'attente automatiques, il se peut que vous devrez uniquement spécifier le routage des appels en de après-heures pour les travailleurs automatiques avec des numéros de téléphone directs.

Si vous souhaitez un routage d'appel distinct pour les appelants en de suite, spécifiez vos heures d'ouverture pour chaque jour. Sélectionnez **Ajouter un nouvel horaire** pour spécifier plusieurs ensembles d'heures pour un jour donné, par exemple pour spécifier une pause déjeuner.

Une fois que vous avez spécifié vos heures d'ouverture, sélectionnez vos options de routage des appels pour les heures de fermeture. Les mêmes options sont disponibles que pour le routage des appels aux heures d'ouverture spécifiés ci-dessus.

Lorsque **vous** avez terminé, sélectionnez Suivant.

## <a name="call-flows-during-holidays"></a>Flux d'appels pendant les jours fériés

![Capture d'écran des paramètres de vœux pour les fêtes de fin d'année](media/auto-attendant-holiday-greeting.png)

Votre employé automatique peut avoir un flux [d'appels](set-up-holidays-in-teams.md)pour chaque jour férié que vous avez installé. Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

1. Dans la page Paramètres d'appel pour les fêtes, sélectionnez **Ajouter.**

2. Tapez un nom pour ce paramètre de congés.

3. Dans la **dropdown** Jours fériés, choisissez les jours fériés que vous voulez utiliser.

4. Choisissez le type de message d'accueil que vous voulez utiliser.

    ![Capture d'écran des paramètres d'action d'appel pour les fêtes](media/auto-attendant-holiday-actions.png)

5. Choisissez si vous voulez **déconnecter ou** **rediriger** l'appel.

6. Si vous choisissez de rediriger l'appel, choisissez sa destination de routage.

7. Sélectionnez **Enregistrer**.

![Capture d'écran des paramètres de congés avec jours fériés répertoriés](media/auto-attendant-holiday-call-settings.png)

Répétez la procédure si nécessaire pour chaque jour férié supplémentaire.

Une fois que vous avez ajouté tous vos jours fériés, sélectionnez **Suivant.**

## <a name="dial-scope"></a>Portée de la numérotation

![Capture d'écran de l'étendue de la numérotation : inclure et exclure des options](media/auto-attendant-dial-scope.png)

*L'étendue de* la numérotation définit les utilisateurs disponibles dans l'annuaire lorsqu'un appelant utilise la numérotation par nom ou la numérotation par extension. La valeur par défaut de **Tous les** utilisateurs en ligne inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne ou hébergés sur site à l'aide de Skype Entreprise Server.

Vous pouvez inclure ou exclure  des utilisateurs  spécifiques en sélectionnant Groupe d'utilisateurs personnalisés sous Inclure ou Exclure, puis en choisissant un ou plusieurs groupes, listes de distribution ou groupes de sécurité Microsoft 365.  Par exemple, vous pouvez exclure des cadres de votre organisation de l'annuaire d'appels. (Si un utilisateur se trouve dans les deux listes, il sera exclu de l'annuaire.)

> [!NOTE]
> Jusqu'à 36 heures peuvent être nécessaire pour que le nom d'un nouvel utilisateur soit répertorié dans l'annuaire.

Lorsque vous avez terminé de définir l'étendue de la numérotation, sélectionnez **Suivant.**

## <a name="resource-accounts"></a>Comptes de ressources

Tous les attendants automatiques doivent avoir un compte de ressource associé.  Les travailleurs automatiques de premier niveau auront besoin d'au moins un compte de ressource associé à un numéro de service. Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un service automatique, chacun avec un numéro de service distinct.

![Capture d'écran du panneau Ajouter des comptes du compte de ressources](media/auto-attendant-add-resource-account.png)

Pour ajouter un compte de ressource, **sélectionnez Ajouter un compte et** recherchez le compte à ajouter. **Sélectionnez** Ajouter, puis **Ajouter.**

![Capture d'écran d'une liste de comptes de ressources affichant le compte de ressource avec le numéro de service affecté](media/auto-attendant-resource-account-assigned.png)

Lorsque vous avez terminé d'ajouter des comptes de service, sélectionnez **Envoyer** pour terminer la configuration du attendant automatique.

## <a name="external-phone-number-transfers---technical-details"></a>Transferts de numéros de téléphone externes - Détails techniques

Reportez-vous [aux conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) pour autoriser les travailleurs automatiques à transférer des appels en externe.  De plus,:

- Pour un compte [](calling-plans-for-office-365.md)de ressource titulaire d'une licence Forfait d'appels, le numéro de téléphone de transfert externe doit être entré au format E.164 (+[code du pays][code de zone][numéro de téléphone]).

- Pour un compte de ressource ayant une licence système téléphonique et une stratégie de routage vocal en ligne de routage direct, le format du numéro de téléphone de transfert externe dépend des paramètres du contrôleur de session en bordure [(SBC).](direct-routing-connect-the-sbc.md)

Le numéro de téléphone sortant affiché est déterminé comme suit :

  - Pour les numéros de plan d'appel, le numéro de téléphone de l'appelant d'origine s'affiche.
  - Pour les numéros de routage direct, le nombre envoyé est basé sur le paramètre P-Ed-Identity (NT) sur le SBC, comme suit :
    - S'il est désactivé, le numéro de téléphone de l'appelant d'origine s'affiche. Il s'agit du paramètre par défaut et recommandé.
    - S'il est activé, le numéro de téléphone du compte de ressource s'affiche.

Dans un environnement hybride Skype Entreprise, pour transférer un appel de moyen de transport automatique vers le réseau PSTN, créez un utilisateur sur site avec le transfert d'appel sur le numéro PSTN. L'utilisateur doit être activé pour les Voix Entreprise une stratégie vocale lui est affectée. Pour en savoir plus, [consultez le transfert d'appel du attendant automatique vers PSTN.](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>Créer un attendant automatique avec PowerShell

Vous pouvez également utiliser PowerShell pour créer et configurer des attendants automatiques. Voici les cmdlets dont vous avez besoin pour gérer un attendant automatique :

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [Nouvelle CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [Nouvelle CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [Nouvelle CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>Rubriques connexes

[Les avantages du système téléphonique](./here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](./getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
