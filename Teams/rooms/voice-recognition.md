---
title: Contrôle Administration du client pour la reconnaissance vocale (profil vocal) dans salles Teams
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur le contrôle Administration des locataires pour la reconnaissance vocale (profil vocal) Teams salles de réunion.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3406e14b64c0c15b2f76a84e42d22a2f726d9b3e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730873"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Gérer les contrôles de technologie de reconnaissance vocale pour un haut-parleur intelligent

Un haut-parleur intelligent utilise les informations de profil vocal pour reconnaître qui a dit quoi dans la transcription en direct. Lorsqu’un Salles Microsoft Teams pour Windows de réunion est équipé d’un haut-parleur intelligent, la transcription en direct peut être utilisée pendant la réunion. Cet article explique comment vous, en tant qu’administrateur de client, contrôlez le profilage vocal utilisé pour la reconnaissance vocale afin de générer une transcription en direct. Vous pouvez contrôler le degré d’utilisation de la reconnaissance vocale par l’organisation et les fonctionnalités suivantes :

- Modifiez le nom du haut-parleur dans les transcriptions.
- Modifiez le haut-parleur d’une seule énoncé de la transcription ou modifiez celui-ci dans toutes les énoncés de la transcription (mais pas sur les transcriptions à venir).
- Modifiez l’identification du haut-parleur pour les personnes qui sont répertoriées dans la réunion.
- Supprimez l’identification d’un ou plusieurs énoncés identifiés en tant que haut-parleur sur chaque transcription.

## <a name="review-intelligent-speaker-requirements"></a>Revoir les exigences de Haut-parleur intelligent

Un haut-parleur intelligent inclut un tableau spécial de sept microphones. Le système utilise les informations de profil vocal pour identifier les voix de 10 personnes au-plus dans les salles de réunion.

Les éléments suivants sont requis pour le haut-parleur intelligent :

- Le client doit être situé aux États-Unis (Amérique du Nord). <sup>1</sup>
- La salle de réunion doit avoir un maximum de 10 personnes présentes en personne.
- La salle de réunion dispose d’un lien de chargement d’au moins 7 Mbits/s.

 <sup>1 Un</sup> haut-parleur intelligent, un profil vocal associé et l’utilisation ne seront disponibles que dans la langue américaine et pour les locataires américains (région NA-US). Les deux conditions doivent être vraies pour qu’un utilisateur client s’inscrive et utilise un haut-parleur intelligent pour une transcription par attributs.

## <a name="set-up-an-intelligent-speaker"></a>Configurer un haut-parleur intelligent

Un haut-parleur intelligent se connecte directement à la console d’salles Teams USB. Pour obtenir de meilleurs résultats, vous devez utiliser un haut-parleur intelligent de la marque Yealink avec une console de marque Yealink.

> [!NOTE]
> Un haut-parleur intelligent Yealink **doit** être utilisé avec une console Yealink.

> [!NOTE]
> Un haut-parleur intelligent connecté à Logitech Surface Pro Salles Microsoft Teams n’est pas Surface Pro Salles Microsoft Teams. Il existe un problème connu qui salles Teams peut pas reconnaître le haut-parleur intelligent par le biais du Dock.

Un haut-parleur intelligent doit être placé à au moins 20 cm des murs et des objets de grande taille, tels que les ordinateurs portables. Si le câble USB Du haut-parleur intelligent n’est pas assez long pour la configuration, utilisez des extensions de câble.

1. Connectez-vous à la console en tant qu’administrateur.
2. Définissez les paramètres Teams de l’appareil pour qu’ils correspondent au micro et au haut-parleur intelligent.
   Vous pouvez également le faire via le portail PRINCIPAL plutôt que via la console de salle.

   Le diagramme montre comment le haut-parleur intelligent est connecté à l’appareil si l’appareil inclut une zone de données.

   ![Configuration du haut-parleur intelligent avec le haut-parleur, la zone d’alimentation et de données. Une ligne passe au port USB de la console, et l’autre est en cours d’alimentation.](../media/intelligent-speakers1.png)

   Le diagramme montre comment le haut-parleur intelligent est connecté à l’appareil si l’appareil n’inclut pas de zone de données.

   ![Configuration du haut-parleur intelligent avec le haut-parleur qui se connecte directement à la console.](../media/intelligent-speakers2.png)

> [!Note]
> Les appareils ANSE et Yealink doivent contenir le préfixe « UAC2_TEAMS » ou « Yealink » et contenir « UAC2_RENDER » dans le nom du haut-parleur et « UAC2_TEAMS » dans le nom du microphone. Si vous ne trouvez pas ces noms de micro et de haut-parleur dans le menu déroulant, redémarrez l’appareil Intelligent Speaker.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Activer la reconnaissance d’un utilisateur Haut-parleur intelligent

Les données de profil vocal peuvent être utilisées dans n’importe quelle réunion avec un haut-parleur intelligent. Pour [plus d’Teams des paramètres de](../meeting-policies-in-teams.md#allow-transcription) réunion, voir les stratégies de réunion powershell et les cmdlets de réunion [PowerShell.](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)

Les données de profil vocal de l’utilisateur sont créées lorsque la stratégie est définie pour faire la distinction ou qu’un invité qui n’est pas en réunion se trouve dans la réunion. Les données de profil vocal sont rejetées à la fin de la réunion.

Voici les stratégies requises pour définir un haut-parleur intelligent et la reconnaissance des utilisateurs.

|Stratégie|Description|Valeurs et comportement|
|-|-|-|
|inscrireUserOverride|Permet de définir la capture de profil vocal, ou l’inscription, Teams paramètres de messagerie pour un client. |**Désactivé**<br><ul><li> Les utilisateurs qui n’ont jamais été inscrits ne peuvent pas afficher, inscrire ou ré-inscrire.<li>Le point d’entrée vers le flux d’inscription est masqué.<li>Si les utilisateurs sélectionnent un lien vers la page d’inscription, un message leur indique que cette fonctionnalité n’est pas activée pour leur organisation.  <li>Les utilisateurs inscrits peuvent afficher et supprimer leur profil vocal dans les Teams messagerie. Une fois qu’il a supprimé son profil vocal, il ne peut plus afficher, consulter ou terminer le flux d’inscription.</li></ul><br>**Activé**<br><ul><li> Les utilisateurs peuvent afficher, consulter et terminer le flux d’inscription.<li>Le point d’entrée s’affiche dans Teams de paramètres de l’onglet **Reconnaissance.**</li></ul>|
|roomAttributeUserOverride|Contrôlez l’identification de l’utilisateur vocal dans les salles de réunion. Ce paramètre est requis pour les salles Teams comptes.| **Désactivé**<br><ul><li>Le salles Teams n’envoie pas de bande passante audio l’enregistrement de flux de la pièce. <li>Les utilisateurs de salle de réunion ne seront pas attribués ou distinctionés, et leurs signatures vocales ne seront pas récupérées ni utilisées.<li>Les utilisateurs de salle de réunion sont inconnus.</li></ul> <br>**Attribut**<br><ul><li>Les utilisateurs des salles seront attribuées en fonction de leur état d’inscription.<li>Le nom des utilisateurs inscrits s’affiche avec leur nom dans la transcription.  <li>Utilisateurs qui ne sont pas inscrits à la conférence en tant que Haut-parleur n.<li>Le salles Teams envoie sept flux audio depuis la salle.</ul> <br>**Distinguer**<br> *Ce paramètre sera disponible à une date ultérieure.*|
|AllowTranscription|Requis pour les comptes d’Teams utilisateur et de salles.|**Vrai** et **Faux**|
||||

Dans le Teams d’administration, définissez la **stratégie Autoriser la transcription.** Paramètres sont **éteints** par défaut.

![Le Centre d’administration avec les stratégies de réunion mises en évidence et Autoriser la transcription sélectionnées.](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Où sont stockées les données de profil vocal ?**

Les données de profil vocal sont stockées dans Office 365 cloud avec le contenu des utilisateurs.

**Quelles sont la chronologie et la stratégie de rétention ?**

La stratégie de rétention générale est indiqué dans la vue [d’ensemble de la rétention des données.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) En outre, les données de profil vocal d’un utilisateur sont supprimées au bout de 3 ans si l’utilisateur n’est invité à aucune réunion avec un haut-parleur intelligent au cours de cette période de 3 ans. Les données ne sont utilisées dans aucune réunion pour les employés existants. Si un employé a quitté l’entreprise, les données de profil vocal sont considérées comme du contenu utilisateur et sont traitées comme tel par Office 365 stratégie de rétention des données décrite dans la vue d’ensemble de la rétention des [données.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

**Les données de profil vocal sont-elles utilisées dans services Microsoft ?**

Non, les données de profil vocal sont utilisées uniquement aux fins dans lesquelles l’utilisateur a fourni son consentement. Microsoft n’utilisera les données de profil vocal qu’Teams de reconnaissance vocale.

Par exemple, Microsoft n’utilise pas les données dans les situations suivantes :

**Les données de mon profil vocal sont-elles utilisées lorsque je rejoins une réunion dans une autre organisation ?**

Non uniquement dans les réunions organisées par un utilisateur de votre organisation.

**Comment exporter mon profil vocal ?**

Votre administrateur informatique peut exporter vos données audio à tout moment.

## <a name="related-topics"></a>Sujets associés

[Article de support : Utiliser des haut-parleurs intelligents pour identifier les participants présents dans la salle ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
