---
title: Contrôle d’administration des locataires pour la reconnaissance vocale (profil vocal) dans salles Teams
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez le contrôle Administration des locataires pour la reconnaissance vocale (profil vocal) dans les salles de réunion Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: 478e739be2787eb2758a2070a441f68c7da727ba
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438302"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Gérer les contrôles de technologie de reconnaissance vocale pour un haut-parleur intelligent

Un haut-parleur intelligent utilise les informations de profil vocal pour reconnaître qui a dit quoi dans la transcription en direct. Lorsqu’un Salles Microsoft Teams sur la salle de réunion Windows est équipé d’un haut-parleur intelligent, la transcription en direct peut être utilisée pendant la réunion. Cet article explique comment vous, en tant qu’administrateur de locataire, contrôlez le profilage vocal utilisé pour la reconnaissance vocale afin de générer une transcription en direct. Vous pouvez contrôler dans quelle mesure l’organisation utilise la reconnaissance vocale et les fonctionnalités suivantes :

- Modifiez le nom de l’orateur dans les transcriptions.
- Modifiez l’orateur d’un seul énoncé dans la transcription ou modifiez l’orateur dans tous les énoncés de la transcription (mais pas sur les transcriptions ultérieures).
- Modifiez l’identification de l’orateur pour les personnes répertoriées dans la réunion.
- Supprimez l’identification d’un ou plusieurs énoncés identifiés comme cet orateur, sur chaque transcription.

## <a name="review-intelligent-speaker-requirements"></a>Passer en revue les exigences relatives aux haut-parleurs intelligents

Un haut-parleur intelligent comprend un réseau spécial de sept microphones. Le système utilise les informations de profil vocal pour identifier les voix d’un maximum de 10 personnes dans les salles de réunion.

Les éléments suivants sont les exigences relatives à l’orateur intelligent :

- La salle de réunion doit avoir un maximum de 10 personnes présentes en personne.
- La salle de réunion a un lien de chargement d’au moins 7 Mbits/s.

Les haut-parleurs intelligents Epos, Sennheiser et Yealink sont pris en charge.

> [!NOTE]
> Intelligent Speaker est disponible dans tous les pays et régions. Consultez [Paramètres régionaux pris en charge](#supported-locales) pour obtenir la liste des paramètres régionaux actuellement pris en charge pour l’inscription biométrique et la transcription en réunion.

## <a name="set-up-an-intelligent-speaker"></a>Configurer un haut-parleur intelligent

Un haut-parleur intelligent se connecte directement via USB à la console salles Teams.

> [!NOTE]
> Un haut-parleur intelligent Yealink **doit** être utilisé avec une console Yealink.

> [!NOTE]
> Nous ne prenons pas en charge un haut-parleur intelligent connecté à Logitech Surface Pro Salles Microsoft Teams. Il existe un problème connu qui salles Teams ne peut pas reconnaître le haut-parleur intelligent via le dock.

Un haut-parleur intelligent doit être placé à au moins 8 pouces (20 cm) des murs et des objets volumineux, tels que les ordinateurs portables. Si le câble USB du haut-parleur intelligent n’est pas assez long pour votre configuration, utilisez des extendeurs de câble.

1. Connectez-vous à la console en tant qu’administrateur.
2. Définissez les paramètres de l’appareil Teams pour qu’ils correspondent au microphone et au haut-parleur intelligents.
   Vous pouvez également le faire via le portail TAC au lieu de la console de la salle.

   Le diagramme montre comment le haut-parleur intelligent est connecté à l’appareil si celui-ci inclut une boîte de données.

   ![Configuration du haut-parleur intelligent avec le haut-parleur, l’alimentation et la boîte de données. Une ligne est acheminée vers le port USB de la console, et l’autre ligne passe à l’alimentation.](../media/intelligent-speakers1.png)

   Le diagramme montre comment le haut-parleur intelligent est connecté à l’appareil si l’appareil n’inclut pas de boîte de données.

   ![Configuration du haut-parleur intelligent avec le haut-parleur se connectant directement à la console.](../media/intelligent-speakers2.png)

> [!NOTE]
> Les dispositifs EPOS et Yealink doivent avoir le préfixe « EPOS » ou « Yealink » et contenir « UAC2_RENDER » dans le nom de l’orateur et « UAC2_TEAMS » dans le nom du microphone. Si vous ne trouvez pas ces noms de microphone et de haut-parleur dans le menu déroulant, redémarrez l’appareil Haut-parleur intelligent.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Activer la reconnaissance utilisateur d’un haut-parleur intelligent

Les données de profil vocal peuvent être utilisées dans n’importe quelle réunion avec un haut-parleur intelligent. Pour plus d’informations sur les paramètres de réunion, consultez Stratégies de [réunions Teams](../meetings-policies-recording-and-transcription.md#transcription) et [applets de commande de réunion PowerShell](/powershell/module/skype/set-csteamsmeetingpolicy) .

Les données de profil vocal de l’utilisateur sont créées lorsque la stratégie est définie pour distinguer ou qu’un invité non-réunion entre pendant la réunion. Les données de profil vocal sont ignorées à la fin de la réunion.

Voici les stratégies requises pour définir un haut-parleur intelligent et une reconnaissance utilisateur.

|Stratégie|Description|Valeurs et comportement|
|-|-|-|
|enrollUserOverride|Utilisez pour définir la capture de profil vocal, ou l’inscription, dans les paramètres Teams d’un locataire. |**Désactivé**<br><ul><li> Les utilisateurs qui ne se sont jamais inscrits ne peuvent pas afficher, inscrire ou réinscrire.<li>Le point d’entrée du flux d’inscription est masqué.<li>Si les utilisateurs sélectionnent un lien vers la page d’inscription, ils verront un message indiquant que cette fonctionnalité n’est pas activée pour leur organisation.  <li>Les utilisateurs inscrits peuvent afficher et supprimer leur profil vocal dans les paramètres Teams. Une fois qu’ils ont supprimé leur profil vocal, ils ne peuvent pas afficher, accéder ou terminer le flux d’inscription.</li></ul><br>**Activé**<br><ul><li> Les utilisateurs peuvent afficher, accéder et terminer le flux d’inscription.<li>Le point d’entrée s’affiche sur la page des paramètres Teams sous l’onglet **Reconnaissance** .</li></ul>|
|roomAttributeUserOverride|Contrôler l’identification de l’utilisateur par la voix dans les salles de réunion. Ce paramètre est requis pour les comptes salles Teams.| **Désactivé**<br><ul><li>L’appareil salles Teams n’envoie pas de bande passante d’économie de flux audio à partir de la salle. <li>Les utilisateurs de salle de réunion ne seront pas attribués ou distingués, et leurs signatures vocales ne seront pas récupérées ou utilisées du tout.<li>Les utilisateurs de salle de réunion sont inconnus.</li></ul> <br>**Attribut**<br><ul><li>Les utilisateurs des salles seront attribués en fonction de leur statut d’inscription.<li>Les utilisateurs inscrits sont affichés avec leur nom dans la transcription.  <li>Les utilisateurs qui ne sont pas inscrits s’affichent en tant qu’orateur \<n>.<li>L’appareil salles Teams enverra sept flux audio à partir de la salle.</ul> <br>**Distinguer**<br> <ul><li>Les utilisateurs des salles seront distingués et séparés comme l’orateur 1, l’orateur 2, .... speaker \<n> dans la transcription.</li><li>Quel que soit l’état d’inscription de l’utilisateur, son nom n’apparaît pas dans la transcription.</li><li>L’appareil salles Teams enverra sept flux audio à partir de la salle.</li></ul>
|AllowTranscription|Obligatoire pour les comptes d’utilisateur et de salles Teams.|**True** et **False**|
||||

Dans le Centre d’administration Teams, définissez la **stratégie de transcription** . Les paramètres sont **désactivés** par défaut.

![le centre d’administration avec les stratégies de réunion mises en surbrillance et l’option Autoriser la transcription sélectionnée.](../media/allow-transcription1.png)
  
> [!NOTE]
> Une fois qu’une stratégie est affectée, son application peut prendre jusqu’à 48 heures. Pour que la stratégie prenne effet plus rapidement, les comptes doivent être déconnectés et reconnecté.

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Où sont stockées les données de profil vocal ?**

Les données de profil vocal sont stockées dans Office 365 cloud avec du contenu utilisateur.

**Quelle est la chronologie et la stratégie de rétention ?**

La stratégie de rétention générale est indiquée dans la [vue d’ensemble de la conservation des données](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview). En outre, les données du profil vocal d’un utilisateur sont supprimées après 1 an si l’utilisateur n’est invité à aucune réunion avec un haut-parleur intelligent au cours de cette période d’un an. Les données ne sont utilisées dans aucune réunion pour les employés existants. Si un employé a quitté l’entreprise, les données de profil vocal sont considérées comme du contenu utilisateur et sont traitées comme telles conformément Office 365 stratégie de conservation des données décrite dans la [vue d’ensemble de la conservation des données](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

**Les données de profil vocal sont-elles utilisées dans Microsoft services ?**

Non, les données de profil vocal sont utilisées uniquement dans le but pour lequel l’utilisateur a donné son consentement. Microsoft n’utiliserez pas les données de profil vocal, sauf dans les scénarios de reconnaissance vocale Teams.

Par exemple, Microsoft n’utiliserez pas les données dans les situations suivantes :

**Mes données de profil vocal sont-elles utilisées lorsque je participe à une réunion dans une autre organisation ?**

Non seulement dans les réunions organisées par un utilisateur de votre organisation.

**Comment puis-je exporter mon profil vocal ?**

Votre administrateur informatique peut exporter vos données audio à tout moment.

## <a name="supported-locales"></a>Paramètres régionaux pris en charge

Les paramètres régionaux d’inscription et de transcription en réunion suivants sont pris en charge dans tous les pays et régions.

### <a name="enrollment-locales"></a>Paramètres régionaux d’inscription

Les utilisateurs finaux peuvent inscrire leurs voix pour la reconnaissance dans les paramètres régionaux suivants :

|**Langue**|**Pays/Région**|**Culture ID**|
|:-----|:-----|:-----|
|Arabe  <br/> |Arabie saoudite <br/> |ar-SA  <br/> |
|Chinois  <br/> |Chine <br/> |zh-CN  <br/> |
|Chinois  <br/> |Taïwan <br/> |zh-TW  <br/> |
|Danois  <br/> |Danemark <br/> |da-DK  <br/> |
|Néerlandais  <br/> |Pays-Bas <br/> |nl-NL  <br/> |
|Anglais  <br/> |Australie <br/> |en-AU  <br/> |
|Anglais  <br/> |Canada  <br/> |en-CA <br/> |
|Anglais  <br/> |Inde  <br/> |en-IN  <br/> |
|Anglais  <br/> |Nouvelle-Zélande  <br/> |en-NZ  <br/> |
|Anglais  <br/> |Royaume-Uni  <br/> |en-GB  <br/> |
|Anglais  <br/> |États-Unis  <br/> |en-US  <br/> |
|Finnois  <br/> |Finlande  <br/> |fi-FI  <br/> |
|Français  <br/> |Canada <br/> |fr-CA  <br/> |
|Français  <br/> |France <br/> |fr-FR  <br/> |
|Italien  <br/> |Italie <br/> |it-IT  <br/> |
|Japonais  <br/> |Japon <br/> |ja-JP  <br/> |
|Norvégien  <br/> |Norvège <br/> |nb-NO  <br/> |
|Polonais  <br/> |Pologne <br/> |pl-PL  <br/> |
|Portugais      <br/> |Brésil <br/> |pt-BR  <br/> |
|Russe  <br/> |Russie <br/> |ru-RU  <br/> |
|Suédois  <br/> |Suède <br/> |sv-SE  <br/> |
|Espagnol  <br/> |Mexique  <br/> |es-MX  <br/> |
|Espagnol  <br/> |Espagne  <br/> |es-ES  <br/> |

### <a name="in-meeting-transcription-locales"></a>Paramètres régionaux de transcription en réunion

Une fois qu’un utilisateur final s’inscrit, sa voix peut être reconnue pendant les réunions et identifiée dans la transcription lorsque la réunion est définie sur l’un des paramètres régionaux suivants :

|**Langue**|**Pays/Région**|**Culture ID**|
|:-----|:-----|:-----|
|Chinois (simplifié)  <br/> |Chine  <br/> |zh-CN  <br/> |
|Anglais  <br/> |Australie <br/> |en-AU  <br/> |
|Anglais  <br/> |Canada  <br/> |en-CA <br/> |
|Anglais  <br/> |Inde  <br/> |en-IN  <br/> |
|Anglais  <br/> |Nouvelle-Zélande  <br/> |en-NZ  <br/> |
|Anglais  <br/> |Royaume-Uni  <br/> |en-GB  <br/> |
|Anglais  <br/> |États-Unis  <br/> |en-US  <br/> |
|Français  <br/> |Canada  <br/> |fr-CA  <br/> |
|Français  <br/> |France  <br/> |fr-FR  <br/> |
|Allemand  <br/> |Allemagne  <br/> |de-DE  <br/> |
|Italien  <br/> |Italie  <br/> | it-IT <br/> |
|Japonais  <br/> |Japon  <br/> |ja-JP  <br/> |
|Coréen  <br/> |Corée  <br/> |ko-KR  <br/> |
|Portugais  <br/> |Brésil  <br/> |pt-BR  <br/> |
|Espagnol  <br/> |Mexique  <br/> |es-MX  <br/> |
|Espagnol  <br/> |Espagne  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>Rubriques connexes

[Article de support : Utiliser des haut-parleurs intelligents pour identifier les participants dans la salle](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
