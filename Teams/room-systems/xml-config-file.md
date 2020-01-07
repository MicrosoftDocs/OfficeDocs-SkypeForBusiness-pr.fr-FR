---
title: Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
description: Cet article décrit la gestion à distance des paramètres par défaut utilisés par un appareil Microsoft Teams, y compris l’application d’un thème personnalisé.
ms.openlocfilehash: 042e62cda753cc622d3b2a6b614d5eca6880a97c
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952457"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML

Cet article décrit la gestion à distance des paramètres par défaut utilisés par un appareil Microsoft Teams, y compris l’application d’un thème personnalisé. Cet article explique comment créer un fichier de paramètres maître et fournit des liens vers des informations sur la façon de les placer selon les besoins sur les appareils gérés à distance.
  
Il est possible de modifier les paramètres par défaut des appareils gérés à distance en mettant à jour un fichier XML maître et en envoyant des copies aux consoles gérées. Vous pouvez également implémenter des thèmes personnalisés sur vos consoles de salle Microsoft teams avec des fichiers de configuration XML.
  
## <a name="create-an-xml-configuration-file"></a>Créer un fichier de configuration XML

Tout éditeur de texte peut être utilisé pour créer un fichier de paramètres. Le tableau d' **éléments XML** décrit les éléments présentés dans cet exemple de fichier de configuration SkypeSettings. XML (nom de fichier requis).
  
```XML
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>file name</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

Si la valeur d’une variable est d’un type incorrect, les éléments ne sont pas mis en ordre, les éléments ne sont pas fermés ou une autre erreur est détectée, le fichier XML est *mal formé*. Lors du traitement d’un fichier XML mal formé, les paramètres trouvés jusqu’au point où l’erreur s’est produite, puis le reste du fichier est ignoré. Tous les éléments inconnus dans le fichier XML sont ignorés. Si un paramètre est omis, il reste inchangé sur l'appareil. Si une valeur de paramètre n’est pas valide, sa valeur antérieure reste inchangée.
  
**Éléments XML**

|Élément|Type|Niveau|Utilisation|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Conteneur de tous les éléments. ||Obligatoire. |
| \<AutoScreenShare\>  |&#x2777; booléenne  |Première &#x2776;  |   Si ce paramètre est vrai, le partage d'écran automatique est activé.  |
|\<HideMeetingName\> |&#x2777; booléenne  |Première &#x2776;  |Si ce paramètre est vrai, les noms de réunion sont masqués. |
|\<UserAccount\> |Conteneur |Première &#x2776;  |Conteneur des paramètres d'identification. L’adresse de connexion, l’adresse Exchange ou l’adresse de messagerie sont généralement les mêmes, par<span></span>exemple RanierConf @contoso. com. |
|\<SkypeMeetingsEnabled\>  |&#x2777; booléenne  |Première &#x2776;  |Activée par défaut. |
|\<SkypeSignInAddress\> |&#x2778; de chaîne  ||Le nom de connexion pour le compte marketing ou teams de la console. |
|\<ExchangeAddress\> |&#x2778; de chaîne  ||Nom de connexion au compte d'appareil Exchange de la console. Si ExchangeAddress est omis, le SkypeSignInAddress ne sera pas réutilisé automatiquement. |
|\<DomainUsername\> |&#x2778; de chaîne  ||Nom de domaine et d'utilisateur de la console, par exemple Seattle\RanierConf. |
|\<Son\> |Chaîne 3  ||  Le paramètre du mot de passe est le même mot de passe que celui utilisé pour la connexion au compte d'appareil Skype Entreprise.   |
| \<ConfigureDomain\>  |&#x2778; de chaîne  ||Vous pouvez répertorier plusieurs domaines, séparés par des virgules. |
|\<TeamsMeetingsEnabled\> |&#x2777; booléenne  |Première &#x2776;  |Désactivé par défaut. <br/> <br/> Le fichier XML est considéré de façon incorrecte\> si\<les\> deux \<SkypeMeetingsEnabled et TeamsMeetingsEnabled sont désactivés, mais il est acceptable d’activer les deux paramètres en même temps. |
|\<IsTeamsDefaultClient> |&#x2777; booléenne  |Première &#x2776;  |Désactivé par défaut. |
|\<BluetoothAdvertisementEnabled> |&#x2777; booléenne  |Première &#x2776;  |Activée par défaut. |
|\<DualScreenMode\>  |&#x2777; booléenne  |Première &#x2776;  |Si la valeur est true, le mode à deux écrans est activé. Dans le cas contraire, l’appareil utilise le mode écran unique. |
|\<SendLogs\> |Conteneur |Première &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\> |&#x2778; de chaîne  || Définit une adresse de messagerie facultative dans laquelle les journaux peuvent être envoyés lorsque la fenêtre « envoyer des commentaires » s’affiche. |
|\<SendLogsAndFeedback\> |&#x2777; booléenne  ||  Si ce paramètre est vrai, les journaux sont envoyés à l'administrateur. Si ce paramètre est faux, seuls les commentaires sont envoyés à l'administrateur (pas les journaux).  |
| \<Appareils\>  |Conteneur |Première &#x2776;  | Les noms des appareils audio connectés dans les éléments enfants sont les mêmes valeurs que celles qui sont répertoriées dans l'application du gestionnaire de périphériques. La configuration peut contenir un appareil qui n'existe pas actuellement sur le système, tel qu'un périphérique audio/vidéo qui n'est pas connecté à la console actuellement. La configuration sera conservée pour l'appareil respectif.  |
|\<MicrophoneForCommunication\> |&#x2778; de chaîne  ||Définit le microphone utilisé comme périphérique d’enregistrement dans une conférence. |
|\<SpeakerForCommunication\> |&#x2778; de chaîne  ||Périphérique qui sera utilisé comme haut-parleur pour la conférence. Ce paramètre permet de définir le périphérique de haut-parleur utilisé dans un appel. |
|\<DefaultSpeaker\> |&#x2778; de chaîne  ||Périphérique qui sera utilisé pour lire le son d'une source de réception HDMI.  |
|\<ContentCameraId>  | &#x2778; de chaîne  | | Définissez le chemin d’accès de l’instance de la caméra configurée dans la salle pour partager du contenu de tableau blanc analogique dans une réunion. Voir [Repérez le chemin d’accès de l’instance de caméra USB](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | &#x2777; booléenne | | Indiquez si l’appareil photo de contenu est physiquement installé à l’envers. Pour les caméras de contenu qui prennent en charge la rotation automatique, spécifiez false. |
|\<ContentCameraEnhancement>  | &#x2777; booléenne | |Lorsque la valeur est définie sur true (valeur par défaut), l’image de l’appareil photo de contenu est améliorée de façon numérique : le bord du tableau blanc est détecté et un zoom approprié est sélectionné, les lignes d’entrée manuscrite sont améliorées et la personne qui rédige le tableau blanc devient transparente.  <br><br> Valeur définie sur false si vous envisagez d’envoyer un flux vidéo brut aux participants d’une réunion pour les espaces dans lesquels un tableau blanc n’est pas dessiné à l’aide d’un stylet et, à la place, la caméra est utilisée pour afficher les notes collantes, les affiches ou tout autre contenu multimédia.  |
| \<Thèmes\>  |Conteneur |Première &#x2776;  |L’une des fonctionnalités qui peuvent être appliquées à un fichier XML est un thème personnalisé pour votre organisation. Vous pouvez spécifier un nom de thème, une image d’arrière-plan et une couleur. |
|\<ThemeName\> |&#x2778; de chaîne  || Permet d'identifier le thème sur le client. Les options pour le nom du thème sont Par défaut, un des thèmes prédéfinis fournis ou Personnalisé. <br/>  Les noms de thème personnalisés utilisent toujours le nom *personnalisé*. L’interface utilisateur du client peut être définie sur la console par défaut ou l’une des présélections, mais l’utilisation d’un thème personnalisé doit être définie à distance par un administrateur. <br/>  Les thèmes prédéfinis sont les suivants :  <br/>  Par défaut <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Pour désactiver le thème actuel, utilisez « aucun thème » pour l’ThemeName.  |
|\<CustomThemeImageUrl\> |&#x2778; de chaîne  ||Requis pour un thème personnalisé, sinon facultatif. Entrez uniquement le nom du fichier.   |Pour plus d’informations sur l’image de thème personnalisé, voir la section [images de thème personnalisées](xml-config-file.md#Themes) .
|\<CustomThemeColor\> |Conteneur ||Conteneur pour les \<valeurs\>RedComponent \<,\>GreenComponent et \<BlueComponent\> . Ces valeurs sont requises pour un thème personnalisé. |
|\<RedComponent\> |Octet (0-255) ||Représente le composant de la couleur rouge. |
|\<GreenComponent\> |Octet (0-255) ||Représente le composant de la couleur verte. |
|\<BlueComponent\> |Octet (0-255) ||Représente le composant de la couleur bleue. |
| | | |

&#x2776; tous les éléments de premier niveau sont facultatifs. Si un élément du premier niveau est omis, tous ses paramètres enfants restent inchangés sur l';appareil.
  
&#x2777; un indicateur booléen peut être : true, false, 0 ou 1. Le fait de laisser des valeurs booléennes ou numériques peut générer le rendu de la valeur XML incorrecte et empêcher les modifications apportées aux paramètres.
  
&#x2778; si un paramètre de chaîne est présent et vide et si vide est une valeur valide, le paramètre est effacé sur l’appareil.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>Gestion des paramètres de la console à l'aide d'un fichier de configuration XML

Au démarrage, si une console Microsoft teams se trouve dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`le fichier XML intitulé SkypeSettings. xml, il applique les paramètres de configuration indiqués par le fichier XML, puis supprime le fichier XML.
  
En fonction du nombre de systèmes de salles de Microsoft teams dont dispose votre entreprise et de la manière dont vous choisissez de les gérer pour les configurer, il existe plusieurs façons de placer le fichier de configuration XML. Une fois le fichier poussé sur la console, redémarrez-la pour traiter les modifications apportées à la configuration. Le fichier de configuration XML est supprimé une fois qu';il a été traité. Les méthodes de gestion suggérées pour les appareils Microsoft teams salles sont décrites dans :
  
- [Configuration d’une stratégie de groupe pour les salles Microsoft teams](room-systems-v2-operations.md#GroupPolicy)
- [Gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#RemotePS) et [configuration d’un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Vous pouvez utiliser la méthode que vous souhaitez tant que vous pouvez l'utiliser pour transférer des fichiers et déclencher un redémarrage sur la console. Le fichier doit être accessible en lecture, en écriture et en suppression par le compte d’utilisateur local de l’appareil. De préférence, il est détenu par et dispose de droits complets accordés à cet utilisateur. Si les autorisations de fichier ne sont pas configurées correctement, le logiciel peut ne pas être en mesure d’appliquer les paramètres, peut ne pas supprimer le fichier en cas de traitement réussi et peut même se bloquer.
  
## <a name="custom-theme-images"></a>Images de thème personnalisées

<a name="Themes"> </a>

Le fichier image de thème personnalisé doit être placé dans`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` le dossier. Entrez le nom et l’extension du fichier \<dans\> la variable CustomThemeImageUrl.
  
Le fichier image doit avoir exactement 3840X1080 pixels et doit être l’un des formats de fichier suivants : jpg, JPEG, png et BMP. Si votre organisation veut utiliser une image personnalisée, un concepteur graphique peut utiliser le [modèle Photoshop thème personnalisé](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd). Il contient de plus amples détails sur l’emplacement des différents éléments de l’interface utilisateur par rapport au reste d’une image de thème et les zones qui apparaissent dans les consoles et les affichages.
  
Le fichier de configuration XML doit être mis à jour lors du démarrage de l'appareil pour reconnaître l'image du thème. Lorsque le nouveau fichier XML est traité et supprimé, le fichier graphique de thème est supprimé de l’annuaire.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Localisez le chemin d’accès à l’instance USB de l’appareil photo de contenu

Pour trouver le chemin d’accès de l’instance :

1. Dans les paramètres Windows, accédez à paramètres Windows dans la console Microsoft teams salles.
2. Entrez le mot de passe d’administrateur.
3. À partir d’une invite de `devmgmt.msc` commandes, tapez pour ouvrir le gestionnaire de périphériques.
4. Dans le **Gestionnaire de périphériques**, recherchez le nœud **Imaging devices** et recherchez l’appareil photo de contenu.
5. Cliquez avec le bouton droit sur l’appareil photo, puis sélectionnez **Propriétés**.
6. Sélectionnez l’onglet **Détails** , puis recherchez la propriété Path de l’instance de l' **appareil** dans la liste déroulante.
7. La valeur affichée correspond au chemin d’accès de l’instance de l’appareil à définir dans le fichier de configuration XML. Lorsque vous spécifiez le chemin d’accès dans XML, remplacez l’esperluette `&amp;`(&) par.

## <a name="see-also"></a>Voir aussi

[Caméras de contenu](content-camera.md)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)

[Configurer un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
