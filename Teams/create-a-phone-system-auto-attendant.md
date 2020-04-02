---
title: Configurer un standard automatique dans le cloud
ms.author: kenwith
author: kenwith
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Découvrez comment configurer et tester les standards automatiques Cloud de Microsoft Teams.
ms.openlocfilehash: 9f166e8626d799cb95a447b453663b60079b0704
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43102083"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurer un standard automatique dans le cloud

Les standards automatiques permettent aux personnes d’appeler votre organisation et de naviguer dans un système de menus pour parler au service approprié, à la file d’attente des appels, à la personne ou à un opérateur. Vous pouvez créer des standards automatiques pour votre organisation à l’aide du centre d’administration Microsoft teams ou avec PowerShell. Pour créer un standard automatique, dans la barre de navigation gauche, sélectionnez **voix** , puis cliquez sur **standards** > automatiques**Ajouter nouveau**.

Pour en savoir plus sur les standards automatiques, reportez-vous à la rubrique [qu’est-ce que les standards automatiques Cloud ?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online.

Les numéros de téléphone ne sont pas directement attribués au standard automatique, mais plutôt à un [compte de ressources](manage-resource-accounts.md) associé au standard automatique.

Les implémentations de standard automatique impliquent souvent plusieurs standards automatiques. Le standard automatique de *premier niveau* possède généralement un compte de ressources avec un numéro de téléphone attribué. Un standard automatique imbriqué est utilisé en tant que menu de second niveau, qui se connecte au standard automatique de *premier niveau* en tant qu’appel de. Il n’est pas nécessaire d’avoir un numéro de téléphone affecté à son compte de ressources pour un standard automatique *imbriqué* .

## <a name="step-1--get-started"></a>Étape 1 : prendre en main

- Un standard automatique est requis pour disposer d’un compte de ressources associé. Pour plus d’informations sur les comptes de ressources et toutes les licences requises, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) . 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne disposant d’une licence de système téléphonique, vous devez l’activer pour Enterprise Voice. Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [affectation de licences Microsoft teams](assign-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>Étape 2 : créer des standards automatiques

> [!IMPORTANT]
> Chaque standard automatique doit disposer d’un compte de [ressources](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer au standard automatique.

### <a name="with-the-microsoft-teams-admin-center"></a>Avec le centre d’administration Microsoft teams

Dans le **Centre d’administration de Microsoft teams**, cliquez sur**standards automatiques** **vocaux** > , puis cliquez sur **+ Ajouter**:

#### <a name="general-info-page"></a>Page informations générales

![Capture d’écran de la page mon standard automatique](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icône du numéro 1, une légende dans le](media/teamscallout1.png)
**nom** de la capture d’écran précédente entrez un nom d’affichage pour votre standard automatique. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris. Le **nom** que vous indiquez ici figure dans une colonne sous l’onglet **standards automatiques** .

<a name="phonenumber"> </a>

* * *

![Icône du numéro 2, une légende dans l'](media/teamscallout2.png)
 <a name="operator"> </a> 
 **opérateur** de capture d’écran précédent il est facultatif (mais recommandé). Vous pouvez définir l’option d' **opérateur** permettant aux appelants de sortir des menus et de parler à une personne désignée.

La touche 0 est affectée à l’opérateur par défaut.

Si vous définissez un opérateur, indiquez aux personnes qui vous appellent à propos de l’option dans les **options de menu modifier** dans la page **flux d’appels** . Si vous définissez un opérateur sur le standard automatique, vous devez entrer le texte d’invite correspondant dans la zone les **appelants entendent** ou changer votre fichier audio pour inclure cette option. Par exemple, « pour l’opérateur, appuyez sur zéro. »

Vous pouvez définir l’opérateur de plusieurs manières :

- **Aucun opérateur** désactive les options « opérateur » et « appuyer sur 0 ». Il s’agit de la valeur par défaut actuelle.
- Une **personne de votre organisation** affecte une personne disposant d’une licence de système téléphonique activée pour les offres d’appels voix entreprise ou affectées dans Office 365. Vous pouvez également le configurer de sorte que l’appelant soit dirigé vers la boîte vocale. Pour envoyer un appel à la boîte vocale, sélectionnez une **personne dans votre organisation** et définissez les paramètres de ce compte pour envoyer les appels directement à la boîte vocale.

     > [!Note]
     > Une **personne de votre organisation** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server.

- **Application vocale**  Sélectionnez le nom du compte de ressources lié à un standard automatique ou une file d’attente d’appels qui a déjà été créée. Les appelants qui demandent un opérateur y sont redirigés.  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![Icône du numéro 3, une légende dans le](media/teamscallout3.png) **fuseau horaire** de capture d’écran précédent vous devez définir le fuseau horaire pour votre standard automatique. Ce paramètre peut être identique à celui de l’adresse principale répertoriée pour votre organisation ou à un fuseau horaire différent. Chaque standard automatique peut avoir un fuseau horaire différent. Les heures d’ouverture définies pour le standard automatique utilisent également ce fuseau horaire. Veillez à définir le fuseau horaire approprié pour éviter les incohérences entre les heures d’entreprise, car certaines régions ne disposent pas de l’heure d’été. 

* * *

![Icône du numéro 4, une légende dans la](media/teamscallout4.png)
 <a name="language"> </a> 
 **langue** précédente de la capture d’écran sélectionnez la langue que vous voulez utiliser pour votre standard automatique. Le standard automatique utilise cette langue avec les appelants, et toutes les invites système sont lues dans cette langue.

 * * *

![Icône du numéro 5, une légende dans la capture d’écran](media/teamscallout5.png)
suivante activer la reconnaissance vocale des**entrées vocales** est disponible si cette option est sélectionnée. Les appelants peuvent utiliser la saisie vocale dans la [langue que vous avez définie](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Si vous souhaitez uniquement permettre aux utilisateurs d’utiliser leur clavier **téléphonique pour effectuer**des sélections, vous pouvez activer la reconnaissance vocale.

* * *  

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**.

#### <a name="call-flow"></a>Flux d’appels

<a name="greetingsandrouting"> </a>

> [!TIP]
> Vous pouvez choisir de configurer un planning d’heures d’entreprise personnalisées, avec des comportements de flux d’appels différents pendant et après les heures d’activité. Pour définir un planning personnalisé, définissez le [flux d’appels facultatif de après les heures](#call-flow-for-after-hours). Par défaut, un standard automatique utilise les flux d’appels d’heures de travail.

Vous pouvez configurer des messages d’accueil personnalisés, des invites et des menus que les utilisateurs entendent quand ils atteignent votre standard automatique.

![Capture d’écran : section Accueil de la page gestion des appels](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**Commencer par lire un message d’accueil** Un message d’accueil est facultatif et peut être défini pour aucun message d' **Accueil**, **lire un fichier audio**ou **taper un message d’accueil**.

> [!NOTE]
> Un message d’accueil est particulièrement utile pour un standard automatique de premier niveau. Le standard automatique imbriqué n’a souvent pas besoin d’un message d’accueil.

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente si vous sélectionnez aucun message d’accueil, l’appelant n’entend **aucun**message ou message d’accueil avant que l’appel ne soit géré par l’une des actions que vous sélectionnez ultérieurement. 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![Icône du numéro 2, une légende dans la capture d’écran](media/teamscallout2.png) précédente si vous sélectionnez **lire un fichier audio** , vous pouvez utiliser le bouton **Télécharger un fichier** pour télécharger un message d’accueil enregistré en tant que fichier audio. WAV,. MP3 ou. Format WMA. Le nombre d’enregistrements ne peut pas dépasser 5 Mo.

![Icône du numéro 3, une légende dans la capture d’écran](media/teamscallout3.png) précédente **tapez un message d’accueil** si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères) dans le champ fourni. Par exemple, entrez «Bienvenue dans contoso. Votre appel est important pour nous. La sortie est créée par un logiciel de synthèse vocale.

* * *

Vous pouvez sélectionner ce qui se produit en regard des appels à partir des actions suivantes dans la section **diriger l’appel** . Les paramètres sont **déconnecter**, **rediriger l’appel**ou **lire les options de menu**.

Si vous sélectionnez **déconnecter**, l’appelant est déconnecté une fois le message d’accueil lu. 

<a name="redirectcalls"> </a>

![Icône du numéro 4, une légende dans la capture d’écran](media/teamscallout4.png) suivante **rediriger l’appel** , envoie l’appelant à la destination choisie sans choisir d’options. Les paramètres possibles sont les suivants :

  - **Personne de l’organisation** Le compte que vous choisissez doit avoir une licence de système téléphonique activée pour voix entreprise ou disposer d’un plan d’appels attribué dans Office 365. Vous pouvez configurer le programme pour qu’il puisse être envoyé à la boîte vocale : sélectionnez une **personne dans l’organisation** et configurer ce compte pour que les appels soient transférés directement à la boîte vocale.

  > [!Note]
  > Une **personne de l’organisation** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server.

  - **Application vocale** Sélectionnez un standard automatique ou une file d’attente d’appels déjà configurée. Vous recherchez le standard automatique ou la file d’attente d’appels en utilisant le nom du compte de ressources associé au service.
  - Boîte **vocale** Sélectionnez le groupe Office 365 qui contient les utilisateurs de votre organisation qui doivent accéder à la boîte vocale reçue par ce standard automatique. Les messages vocaux sont envoyés au groupe Office 365 que vous avez spécifié. Pour accéder aux messages vocaux, les membres du groupe peuvent les ouvrir en accédant au groupe dans Outlook.

      Basculez la **transcription** sur **activé** pour activer la transcription vocale des messages vocaux.

 * * *

![Capture d’écran : section actions de la page gestion des appels](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente lorsque vous sélectionnez **lire les options de menu** , vous pouvez choisir d’utiliser un fichier audio ou d’entrer du texte qui sera affiché en tant que texte par synthèse vocale afin d’offrir des options de menu de type pavé numérique aux appelants. Sélectionnez cette option au lieu de **Rediriger** les options appeler ou **déconnecter** .


![Icône du numéro 2, une légende dans la capture d’écran](media/teamscallout2.png) précédente **lire un fichier audio** vous permet de configurer une invite et des options pour l’appelant. 
- Si vous sélectionnez **lire un fichier audio** , vous pouvez utiliser le bouton **Télécharger un fichier** pour télécharger un message d’accueil enregistré en tant que fichier audio. WAV,. MP3 ou. Format WMA. Le nombre d’enregistrements ne peut pas dépasser 5 Mo.

- **Taper un message d’accueil** Si vous choisissez cette option, entrez le texte que le système doit lire (jusqu’à 1000 caractères) dans le champ fourni. Par exemple, entrez «Bienvenue dans contoso. Votre appel est important pour nous. La sortie est créée par un logiciel de synthèse vocale.

**Définir les options de menu** Le clavier téléphonique ou les commandes vocales peuvent être ajoutés ou supprimés dans cette boîte de dialogue. Pour supprimer une option de menu, supprimez l’entrée de commande vocale, puis **redirigez** vers retour pour **Sélectionner**.

> [!TIP]
> Mettez à jour le texte d’invite de menu ou réenregistrez les invites audio lorsque vous supprimez des options. L’invite de menu lue pour les appelants n’est pas automatiquement mise à jour.  
>
> Toutes les options de menu peuvent être ajoutées et supprimées dans n’importe quel ordre, et les mappages de clés ne doivent pas nécessairement être continus. Par exemple, il est possible de créer un menu avec les clés 0, 1 et 3 mappées à des options, tandis que la clé 2 n’est pas utilisée.

> [!NOTE]
> Les clés \* (répétition) et \# (retour) sont réservées par le système et ne peuvent pas être réaffectées. Si la reconnaissance vocale est activée, le fait d’appuyer sur * correspond à « répéter » et # correspond aux commandes vocales « retour ».

![Icône du numéro 3, une légende dans la capture d’écran](media/teamscallout3.png) précédente pour configurer une option de menu, cliquez sur **+ affecter une touche de numérotation** , puis entrez les informations pour les options suivantes :

![Icône du numéro 4 ; une légende dans la capture d’écran](media/teamscallout4.png)de la**commande vocale** de la capture initiale pour une option peut comporter jusqu’à 64 caractères et contenir plusieurs mots tels que « service clientèle » ou « opérations et raisons ».   Si la reconnaissance vocale est activée, le nom est automatiquement reconnu et l’appelant est en mesure d’appuyer sur 3, de dire « trois » ou de « service clientèle » pour sélectionner l’option associée à la clé 3. Ce texte est également affiché par synthèse vocale pour l’invite de confirmation du service (par exemple, « transfert de votre appel vers l’opérateur »).

![Icône du numéro 5, une légende dans la capture d’écran](media/teamscallout5.png) précédente les options **Rediriger vers** l’emplacement de l’appel, si la touche correspondante est enfoncée ou si l’option est activée à l’aide de la reconnaissance vocale. L’appel peut être envoyé à :

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **Opérateur** Si un opérateur est déjà configuré, l’option est automatiquement mappée à la clé 0, mais peut également être supprimée ou réaffectée à une autre clé. L’appelant qui sélectionne cette option est envoyé à l’opérateur désigné. Si l’opérateur n’est pas défini sur une touche, la commande vocale « opérateur » est également désactivée. 
- Une **personne de l’organisation** peut être un utilisateur en ligne ou un utilisateur hébergé sur site utilisant Skype entreprise Server. L’utilisateur doit disposer d’une licence de système téléphonique activée pour les offres d’appels voix entreprise ou affectées dans Office 365. Recherchez la personne dans le champ **Rechercher par nom** .

- **Application vocale** Sélectionnez un standard automatique ou une file d’attente d’appels déjà configurée. Vous recherchez le standard automatique ou la file d’attente d’appels en utilisant le nom du compte de ressources associé à l’application.

- Boîte **vocale** Sélectionnez le groupe Office 365 qui contient les utilisateurs de votre organisation qui doivent accéder à la boîte vocale reçue par ce standard automatique. Les messages vocaux sont envoyés au groupe Office 365 que vous avez spécifié. Pour accéder aux messages vocaux, les membres du groupe peuvent les ouvrir en accédant au groupe dans Outlook.

    Basculez la **transcription** sur **activé** pour activer la transcription vocale des messages vocaux.

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![Icône du numéro 6, une légende dans la capture d’écran](media/teamscallout6.png)précédente de la**recherche** dans cette section, vous pouvez activer le **numérotation par nom** et la **numérotation par poste** pour le standard automatique.   Vous pouvez définir qui est et non inclus dans ces services dans la page de portée de numérotation facultative. La recherche dans l’annuaire est définie sur **aucune** par défaut.

**Numérotation par nom** Si vous activez cette option, les appelants peuvent rechercher des personnes dans votre organisation à l’aide de la **numérotation par nom**. Il parle du nom de l’utilisateur et de la reconnaissance vocale à l’utilisateur. Vous pouvez définir qui est et non inclus dans ces services dans la page de portée de numérotation facultative. Tout utilisateur en ligne disposant d’une licence de système téléphonique ou d’un utilisateur hébergé sur site utilisant Skype entreprise Server est éligible et est disponible avec la numérotation par nom.


**Composer par poste** Si vous activez cette option, les appelants peuvent se connecter aux utilisateurs de votre organisation en entrant leur numéro de poste. Vous pouvez sélectionner les utilisateurs qui sont répertoriés comme étant disponibles ou qui ne sont pas disponibles pour **composer par poste** dans la page d’étendue de numérotation facultative. Tout utilisateur en ligne disposant d’une licence de système téléphonique ou d’un utilisateur hébergé sur site utilisant Skype entreprise Server est éligible et peut être trouvé avec la numérotation par poste.

> [!IMPORTANT]
> Notez ce qui suit :
>- Les utilisateurs que vous souhaitez rendre disponibles pour la numérotation par poste de poste doivent avoir une extension spécifiée dans le cadre de l’un des attributs de téléphone suivants définis dans Active Directory ou le centre d’administration Azure Active Directory [Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users).
>    - HomePhone
>    - Mobile/MobilePhone
>    - TelephoneNumber/PhoneNumber
>    - OtherTelephone
>- Le format requis pour entrer l’extension dans le champ numéro de téléphone de l’utilisateur `+<phonenumber>;ext=<extension>` est `x<extension>`soit ou.
>- L’attribution d’une extension dans le centre d’administration teams n’est pas prise en charge pour le moment. Vous devez utiliser la commande PowerShell [Set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) ou le centre d’administration Microsoft 365.
>- Il est possible que les modifications apportées aux attributs AAD et MobilePhone soient jusqu’à 12 heures.
>- Ne définissez pas d’extension pour le LineUri d’un utilisateur. Cette fonctionnalité n’est pas prise en charge pour le moment.
>- Un standard automatique peut être configuré pour composer par nom ou par numéro de poste, mais pas les deux.

> [!NOTE]
> Si vous voulez utiliser les fonctions **numérotation par nom** et **numéro de poste par numéro** , vous pouvez créer le standard automatique principal (activé pour la **numérotation par nom**) qui invite les appelants à choisir une option de menu si elles connaissent l’extension de l’utilisateur et définir cette option pour transférer l’appel vers un standard automatique activé pour la numérotation par poste.

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

Lorsque vous avez terminé vos sélections, vous pouvez cliquer sur **suivant** si vous voulez modifier les paramètres avancés ou cliquer sur le **faire si vous** souhaitez utiliser les paramètres par défaut pour les éléments suivants :
- Flux d’appels pour après heures
- Flux d’appels pour les jours fériés
- Étendue de numérotation
- Comptes de ressources

Dans la mesure où votre standard automatique est requis pour disposer d’un compte de ressources, vous pouvez passer à la page du **compte de ressources** et associer un compte de ressources que vous avez déjà configuré, ou créer un compte de ressource et l’associer au standard automatique comme décrit dans [gérer les comptes de ressources dans Microsoft teams](manage-resource-accounts.md). Vous ne serez pas en mesure d’utiliser ce standard automatique tant qu’il n’a pas été associé à un compte de ressources. pour cela, cliquez sur le bouton **suivant** en bas de l’écran, puis cliquez sur **comptes de ressources** dans le volet de navigation de gauche pour accéder directement à la page comptes de ressources et associez le standard automatique à un compte de ressources.

#### <a name="advanced-settings-optional"></a>Advanced Settings (facultatif)

Il existe quatre écrans supplémentaires que vous pouvez configurer ou laisser par défaut à votre choix.

##### <a name="call-flow-for-after-hours"></a>Flux d’appels pour après heures

Par défaut, les heures d’activité d’un standard automatique sont définies sur 9H-17h00, du lundi au vendredi.  <!--24/7-->et les options de flux d’appels pour les appels *après les heures* sont désactivées parce que toutes les heures sont considérées comme des *heures de travail*. Lorsque vous sélectionnez l’option **configurer les heures d’ouverture personnalisées** , le **flux d’appels pour** la page après les heures configure les règles de traitement des appels utilisées par le standard automatique après les heures. Les options disponibles sont les mêmes, la différence est la possibilité de définir un planning pour différents menus et comportements.

Un système de standards automatiques doit uniquement définir le comportement de gestion des appels d’après-service pour le standard automatique de premier niveau. Les standards automatiques imbriqués peuvent ne pas être appelés par le standard automatique de premier niveau, mais le système peut également définir un comportement d’après-heures pour chaque standard automatique qu’il utilise.

Au départ, les heures d’ouverture sont définies pour commencer à 12:00 AM et se terminent à 12:00 PM, dimanche à samedi. Toutes les heures qui ne sont pas au cours des heures d’activité sont considérées comme des *heures passées*.


![capture d’écran des paramètres de flux d’appels après heures](media/aa-afterhour.png)
 * * *

![Dans la capture d’écran du numéro 1, une légende dans](media/teamscallout1.png) la capture d’écran précédente, vous pouvez cliquer sur **Sélectionner 24/7** pour afficher toutes les heures d’activité pour ce standard automatique.

![Dans le numéro 2, une légende dans la capture d’écran](media/teamscallout2.png) précédente, sélectionnez l’option de **réinitialisation par défaut** pour rétablir toutes les modifications apportées à la planification et revenir à la définition par défaut des heures d’activité, de 9:00 à 5:00 PM du lundi au vendredi.

![Icône du numéro 3 ; une légende dans la capture d’écran](media/teamscallout3.png) précédente sélectionnez **effacer toutes les heures** pour effacer entièrement le planning. Si vous sélectionnez cette option et que vous ne souhaitez pas utiliser les heures non configurées, utilisez cette option uniquement si vous voulez recommencer entièrement les heures d’activité.

![Icône du numéro 4, une légende dans l’icône précédent de](media/teamscallout4.png)![la capture d’écran, une légende dans la capture d’écran](media/teamscallout5.png) précédente pour personnaliser l’heure de début ou de fin d’un jour de la semaine, cliquez sur au **début ou à** la fin de l’heure de début et de **fin** de la liste qui s’affiche.   La liste permet de sélectionner des heures d’ouverture par intervalle de 15 minutes, et les heures d’ouverture sélectionnées ici dépendent du fuseau horaire que vous avez défini dans la page **informations générales** .

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![Icône du numéro 6, une légende dans la capture d’écran](media/teamscallout6.png) précédente pour configurer un saut (par exemple, une pause déjeuner, par exemple), sélectionnez **Ajouter une nouvelle heure** pour ce jour de la semaine pour créer une ligne de tableau, puis sélectionnez nouvelles heures de début et de fin. Vous pouvez définir plusieurs sauts dans les heures de bureau.

Les options de [flux d’appels](#call-flow) disponibles après les heures sont les mêmes que celles disponibles pendant les heures d’activité. Faire défiler la page d’entrée d’information pour définir les options de flux d’appels après heures.

* * *

Lorsque vous avez terminé vos sélections, cliquez sur **suivant**. Vous pouvez également cliquer sur **comptes de ressources** dans le volet de navigation de gauche pour accéder directement à la page comptes de ressources et associer le standard automatique à un compte de ressources.

##### <a name="call-flow-during-holidays"></a>Flux d’appels pendant les vacances

<a name="holidaygreetings"> </a>

Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique. Il est possible que votre organisation ait déjà défini des jours fériés comme décrit dans la rubrique [configurer les jours fériés dans Microsoft teams](set-up-holidays-in-teams.md). Si ce n’est pas le cas, l’écran suivant apparaît : 

![Capture d’écran : aucun congé configuré](media/aa-no-holidays.png)

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente pour définir un flux d’appels personnalisé pour un jour férié sur le standard automatique, cliquez sur **+ Ajouter** l’écran de **nouveau flux d’appels de vacances** .
> [!TIP]
> Pour créer des jours fériés **,** > vous pouvez accéder à l’écran aux**jours fériés**de l’organisation.  



![Capture d’écran : ajouter un gestionnaire d’appels](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente entrez un **nom** pour le nouveau flux d’appels.

![Icône du numéro 2, une légende dans la capture d’écran](media/teamscallout2.png) précédente si vous avez déjà créé des jours fériés, vous les verrez dans le menu déroulant des **fêtes** et pouvez les sélectionner. Vous verrez peut-être une option inutilisée que vous pouvez modifier selon vos besoins. Si ce n’est pas le cas, cliquez sur **Ajouter** au bas de la liste déroulante pour créer un jour férié.  Pour plus d’informations sur les étapes de création d’un congé, voir [configurer les jours fériés dans Microsoft teams](set-up-holidays-in-teams.md) . 

Le nom d’un flux d’appels de vacances peut contenir jusqu’à 64 caractères et doit être unique pour l’organisation. Par exemple, vous ne pouvez pas avoir deux flux d’appels de vacances nommés « Thanksgiving » dans la même organisation. Le standard automatique peut faire un flux d’appels pour chaque jour férié que vous avez configuré, mais il se peut que vous souhaitiez disposer d’un ensemble de comportements communs qui n’est pas une formule de salutation personnalisée.

![Icône du numéro 3, une légende dans la capture d’écran](media/teamscallout3.png) précédente les options d' [Accueil](#call-flow) disponibles pour un flux d’appels de vacances sont les mêmes que celles disponibles pendant les heures d’activité. Les **actions** effectuées après le message d’accueil sont également similaires, sauf que les seules actions disponibles sont la **déconnexion** ou la **redirection vers**, et lorsque vous sélectionnez l’option **Rediriger vers** , l’opérateur n’est pas l’un des choix disponibles. Vous ne pouvez pas définir un menu spécifique à un flux de vacances.

> [!NOTE]
> Par défaut, tous les appels reçus pendant une période de vacances sont définis pour **déconnecter** après le message d’accueil (le cas échéant), vous devez donc spécifier une redirection si vous souhaitez un comportement personnalisé.

![Capture d’écran de la page du flux d’appels sur les jours fériés](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

Cliquez sur Enregistrer pour terminer la création du flux d’appels de vacances. Une fois que vous avez créé un flux d’appels de vacances, il s’affiche sur l’écran du **flux d’appels** .

Cliquez sur en **regard** de définir l’étendue de numérotation, de **nouveau** pour modifier les flux d’appels d’après les heures et de l' **envoi** si vous avez terminé. Vous pouvez également cliquer sur **comptes de ressources** dans le volet de navigation de gauche pour accéder directement à la page comptes de ressources et associer le standard automatique à un compte de ressources.

#### <a name="dial-scope"></a>Étendue de numérotation

<a name="dialscope"> </a>

![Capture d’écran montrant la page de portée de numérotation](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

Dans cette page, vous pouvez définir qui est répertorié dans votre annuaire et disponible pour le numérotation par nom lorsque quelqu’un appelle votre organisation. La numérotation par nom est définie sur **désactivé** par défaut dans un écran antérieur. Tous les utilisateurs disposant d’une extension seront disponibles si la **numérotation par poste** a été sélectionnée auparavant.

![D’après le numéro 1, une légende dans la capture d'](media/teamscallout1.png) écran précédente **inclut** les options de cette section : **tous les utilisateurs en ligne** ou **groupes d’utilisateurs personnalisés**

Si vous sélectionnez **tous les utilisateurs en ligne**, tous les utilisateurs éligibles sont inclus dans la recherche dans l’annuaire.

**Groupes d’utilisateurs personnalisés** Cette option vous permet de rechercher et de sélectionner un groupe Office 365, une liste de distribution ou un groupe de sécurité déjà créé au sein de votre organisation. Les utilisateurs sont ajoutés à l’annuaire s’ils se trouvent dans le groupe Office 365 sélectionné, une liste de distribution ou un groupe de sécurité, et qu’il s’agit des **utilisateurs en ligne disposant d’une licence de système téléphonique** ou hébergé sur site via Skype entreprise Server. Vous pouvez ajouter plusieurs groupes Office 365, des listes de distribution et des groupes de sécurité à l’annuaire.

<a name="dialscope"> </a>

Dans cette page, vous pouvez configurer les utilisateurs de votre organisation qui seront répertoriés dans votre annuaire et disponibles pour le numérotation par nom lorsqu’une personne appelle votre organisation.

![Icône du numéro 2, une légende dans la capture d’écran](media/teamscallout2.png) précédente **exclue** les options de cette section vous permettent d’exclure des utilisateurs ou des groupes d’utilisateurs spécifiques de l’annuaire de l’organisation.

Si vous sélectionnez **aucun**, tous les utilisateurs éligibles sont inclus dans la recherche dans l’annuaire.

**Groupe d’utilisateurs personnalisés** Vous pouvez rechercher un groupe Office 365, une liste de distribution ou un groupe de sécurité créé au sein de votre organisation. Les utilisateurs de ce groupe sont exclus de la recherche dans l’annuaire. Vous pouvez ajouter plusieurs groupes 365 Office, des listes de distribution et des groupes de sécurité.


Si vous spécifiez les paramètres par défaut lorsque la numérotation par nom est activée, tous les utilisateurs éligibles sont inclus dans la recherche dans l’annuaire.

> [!NOTE]
> Le nom d’un nouvel utilisateur peut nécessiter un maximum de 36 heures. Lorsque quelqu’un utilise la numérotation par nom avec la reconnaissance vocale, il est possible que les nouveaux comptes ne soient pas disponibles pour cette fonctionnalité.

Après avoir entré tous les champs requis et configuré l’ensemble des menus et options de traitement des appels, cliquez sur **suivant** pour passer à l’Association d’un compte de ressource.

#### <a name="resource-accounts"></a>Comptes de ressources

Tous les standards automatiques doivent disposer d’un compte de ressources associé.  Les standards automatiques de premier niveau ont besoin d’au moins un compte de ressources pour lequel un numéro de service est associé. Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un standard automatique, chacun avec un numéro de service distinct.

Si vous n’avez pas encore configuré de compte de ressources pour votre standard automatique, l’écran suivant apparaît : 

![capture d’écran : gestion de compte de ressources facultative](media/aa-ra-optional.png) 

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente pour ajouter un ou plusieurs comptes de ressources existants et non attribués au standard automatique, cliquez sur **Ajouter un compte** , puis sur Rechercher et sélectionnez-le dans les boîtes de dialogue fournies.

![capture d’écran de l’affichage de synthèse nouveau standard](media/aa-assigned.png)

![Icône du numéro 1, une légende dans la capture d’écran](media/teamscallout1.png) précédente pour ajouter un compte de ressources supplémentaire, cliquez sur **+ Ajouter un compte**.

![Icône du numéro 2, une légende dans la capture d’écran précédente](media/teamscallout2.png) Le compte de ressources ou les comptes attribués à ce standard automatique apparaissent dans une liste.

## <a name="edit-auto-attendants"></a>Modifier des standards automatiques

Une fois que vous avez enregistré votre nouveau standard automatique, il apparaît dans la page **standards automatiques** . Cette page vous permet de voir rapidement certaines des options que vous avez configurées, y compris le nom, le compte de ressources associé, la langue et l’opérateur affecté.

![capture d’écran de la liste d’attendant](media/aa-list.png)

Si vous voulez modifier les paramètres du standard automatique, sélectionnez le standard automatique, puis dans le volet action, cliquez sur **modifier**.

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>Créer un standard automatique avec PowerShell

Vous pouvez également utiliser PowerShell pour créer et configurer des standards automatiques. Voici les applets de passe dont vous avez besoin pour gérer un standard automatique :

- [Nouveau-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [Nouveau-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [Nouveau-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [Nouveau-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [Nouvelle CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [Nouvelle CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [Nouvelle CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [Nouveau-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Importation-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [Nouveau-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Office 365 et Microsoft teams à partir d’un point d’administration unique qui peut simplifier le travail quotidien. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité qui consiste à utiliser le centre d’administration Microsoft 365, par exemple pour apporter des changements de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Voir aussi

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtention de numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Nouvelle CsOrganizationalAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Un standard Cloud automatique, qu’est-ce que c’est ?](what-are-phone-system-auto-attendants.md)

[Exemple petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)  
