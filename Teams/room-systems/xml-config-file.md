---
title: Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: Cet article décrit la gestion à distance des paramètres par défaut utilisés par un appareil Microsoft Teams, y compris l’application d’un thème personnalisé.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305332"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML
 
Cet article décrit la gestion à distance des paramètres par défaut utilisés par un appareil Microsoft Teams, y compris l’application d’un thème personnalisé.
  
En modifiant un fichier XML maître et en envoyant des copies aux consoles que vous gérez, vous pouvez modifier les paramètres par défaut des appareils gérés à distance. Cet article explique comment créer ce type de fichier et fournit des liens vers des discussions indiquant comment les placer selon vos besoins sur les appareils gérés à distance. À l’aide de cette méthode, vous pouvez également implémenter des thèmes personnalisés sur vos consoles Microsoft teams salles. 
  
## <a name="creating-an-xml-configuration-file"></a>Création d'un fichier de configuration XML

Le tableau ci-dessous décrit les éléments présentés dans cet exemple de fichier de configuration SkypeSettings. Xml. 
  
```
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
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

Si le fichier XML est formé de manière incorrecte (le type d'une valeur de variable est incorrect, des éléments ne sont pas dans l'ordre correct, des éléments sont non fermés, etc.), les éléments jusqu'au point où l'erreur est détectée sont appliqués, puis le reste du fichier est ignoré lors du traitement. Tous les éléments inconnus dans le fichier XML sont ignorés. Si un paramètre est omis, il reste inchangé sur l'appareil. Si la valeur d’un paramètre n’est pas valide, sa valeur antérieure reste inchangée.
  
**Éléments XML**
 
|Élément|Type|Niveau|Utilisation|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Conteneur de tous les éléments.   ||Obligatoire.   |
| \<AutoScreenShare\>  |Valeur & # x2777;  |Premier & # x2776;  |   Si ce paramètre est vrai, le partage d'écran automatique est activé.  |
|\<HideMeetingName\>   |Valeur & # x2777;  |Premier & # x2776;  |Si ce paramètre est vrai, les noms de réunion sont masqués.   |
|\<UserAccount\>   |Conteneur   |Premier & # x2776;  |Conteneur des paramètres d'identification.   L’adresse de connexion, l’adresse Exchange ou l’adresse de messagerie sont généralement les mêmes, par<span></span>exemple RanierConf @contoso. com.   |
|\<SkypeMeetingsEnabled\>  |Valeur & # x2777;  |Premier & # x2776;  |Activée par défaut.   |
|\<SkypeSignInAddress\>   |Chaîne & # x2778;  ||Nom de connexion au compte d'appareil Skype Entreprise de la console.   |
|\<ExchangeAddress\>   |Chaîne & # x2778;  ||Nom de connexion au compte d'appareil Exchange de la console.   Si l'adresse d'Exchange est omise, l'adresse de connexion à Skype ne sera pas réutilisée automatiquement.    |
|\<DomainUsername\>   |Chaîne & # x2778;  ||Nom de domaine et d'utilisateur de la console, par exemple Seattle\RanierConf.   |
|\<Son\>   |Chaîne 3  ||  Le paramètre du mot de passe est le même mot de passe que celui utilisé pour la connexion au compte d'appareil Skype Entreprise.   |
| \<ConfigureDomain\>  |Chaîne & # x2778;  ||Vous pouvez répertorier plusieurs domaines, séparés par des virgules.   |
|\<TeamsMeetingsEnabled\>   |Valeur & # x2777;  |Premier & # x2776;  |Désactivé par défaut. <br/> <br/> Le fichier XML est considéré de façon incorrecte\> si\<les\> deux \<SkypeMeetingsEnabled et TeamsMeetingsEnabled sont désactivés, mais il est acceptable d’activer les deux paramètres en même temps.   |
|\<IsTeamsDefaultClient> |Valeur & # x2777;  |Premier & # x2776;  |Désactivé par défaut. |
|\<BluetoothAdvertisementEnabled> |Valeur & # x2777;  |Premier & # x2776;  |Activée par défaut. |
|\<DualScreenMode\>  |Valeur & # x2777;  |Premier & # x2776;  |Si la valeur est true, le mode à deux écrans est activé. Dans le cas contraire, l'appareil utilisera le mode d'écran unique.   |
|\<SendLogs\>   |Conteneur   |Premier & # x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Chaîne & # x2778;  ||Ce paramètre définit une adresse électronique en option à laquelle les journaux peuvent être envoyés lorsque la fenêtre "Envoyer des commentaires" s'affiche.    |
|\<SendLogsAndFeedback\>   |Valeur & # x2777;  ||  Si ce paramètre est vrai, les journaux sont envoyés à l'administrateur. Si ce paramètre est faux, seuls les commentaires sont envoyés à l'administrateur (pas les journaux).  |
| \<Appareils\>  |Conteneur   |Premier & # x2776;  | Les noms des appareils audio connectés dans les éléments enfants sont les mêmes valeurs que celles qui sont répertoriées dans l'application du gestionnaire de périphériques. La configuration peut contenir un appareil qui n'existe pas actuellement sur le système, tel qu'un périphérique audio/vidéo qui n'est pas connecté à la console actuellement. La configuration sera conservée pour l'appareil respectif.  |
|\<MicrophoneForCommunication\>   |Chaîne & # x2778;  ||Définit le microphone qui sera utilisé comme appareil d'enregistrement dans une conférence.   |
|\<SpeakerForCommunication\>   |Chaîne & # x2778;  ||Périphérique qui sera utilisé comme haut-parleur pour la conférence. Ce paramètre permet de définir le haut-parleur qui sera utilisé pour entendre le son lors d'un appel.   |
|\<DefaultSpeaker\>   |Chaîne & # x2778;  ||Périphérique qui sera utilisé pour lire le son d'une source de réception HDMI.    |
| \<Thèmes\>  |Conteneur   |Premier & # x2776;  |Une des fonctionnalités qui peuvent être appliquées en utilisant un fichier XML est un thème personnalisé pour votre organisation. Vous pourrez spécifier un nom de thème, une image d’arrière-plan et une couleur.   |
|\<ThemeName\>   |Chaîne & # x2778;  || Permet d'identifier le thème sur le client. Les options pour le nom du thème sont Par défaut, un des thèmes prédéfinis fournis ou Personnalisé. <br/>  Les noms de thème personnalisés doivent toujours utiliser le nom *personnalisé* . L';interface utilisateur du client peut être définie sur la console sur Par défaut ou l';un des thèmes prédéfinis, mais l';application d';un thème personnalisé doit être définie à distance par Administrateur. <br/>  Les thèmes prédéfinis sont les suivants :  <br/>  Par défaut <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Pour désactiver le thème actuel, utilisez «aucun thème» pour l’ThemeName.  |
|\<CustomThemeImageUrl\>   |Chaîne & # x2778;  ||Obligatoire si vous utilisez un thème personnalisé, sinon facultatif. Pour plus d’informations sur l’image de thème personnalisé, voir la section [images de thème personnalisées](xml-config-file.md#Themes) ci-dessous.  |
|\<CustomThemeColor\>   |Conteneur   ||Conteneur pour les \<valeurs\>RedComponent \<,\>GreenComponent et \<BlueComponent\> . Ces valeurs sont obligatoires si un thème personnalisé est utilisé.   |
|\<RedComponent\>   |Octet (0-255)   ||Représente le composant de la couleur rouge.   |
|\<GreenComponent\>   |Octet (0-255)   ||Représente le composant de la couleur verte.   |
|\<BlueComponent\>   |Octet (0-255)   ||Représente le composant de la couleur bleue.   |
| | | |
   
&#x2776; Tous les éléments de premier niveau sont facultatifs. Si un élément du premier niveau est omis, tous ses paramètres enfants restent inchangés sur l';appareil.
  
&#x2777; Un indicateur booléen peut être l’un des éléments suivants: true, false, 0 ou 1. Des valeurs booléennes ou numériques laissées vides peuvent rendre le fichier XML incorrect, et les paramètres ne seront donc pas modifiés.
  
 &#x2778; Si un paramètre de chaîne est présent, vide et vide est une valeur valide, le paramètre est effacé sur l’appareil.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Gestion des paramètres de la console à l'aide d'un fichier de configuration XML

Au démarrage, si une console Microsoft teams vous permet de rechercher un fichier XML intitulé SkypeSettings. XML à l’emplacement **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, il applique les paramètres de configuration indiqué par le fichier XML, puis supprimez le fichier XML.
  
En fonction du nombre de systèmes de salles de Microsoft teams dont dispose votre entreprise et de la manière dont vous choisissez de les gérer pour les configurer, il existe différentes façons de placer le fichier de configuration XML. Une fois le fichier poussé sur la console, redémarrez-la pour traiter les modifications apportées à la configuration. Le fichier de configuration XML est supprimé une fois qu';il a été traité. Les méthodes de gestion suggérées pour les appareils Microsoft teams salles sont décrites dans:
  
- [Configuration d’une stratégie de groupe pour les salles Microsoft teams](room-systems-v2-operations.md#GroupPolicy)
    
- [Gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#RemotePS) et [configuration d’un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Vous pouvez utiliser la méthode que vous souhaitez tant que vous pouvez l'utiliser pour transférer des fichiers et déclencher un redémarrage sur la console. Le fichier doit être accessible en lecture, en écriture et en suppression par le compte d’utilisateur local de l’appareil (de préférence, il doit être détenu par et disposer de droits complets accordés à cet utilisateur). Si les autorisations du fichier ne sont pas définies correctement, le logiciel risque de ne pas pouvoir appliquer les paramètres après le traitement réussi de celui-ci et éventuellement se bloquer.
  
## <a name="custom-theme-images"></a>Images de thème personnalisées
<a name="Themes"> </a>

Le fichier image de thème personnalisé doit être placé dans **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, il vous suffit d’entrer le nom de \<fichier\> et l’extension dans la variable CustomThemeImageUrl.
  
Le fichier image doit être exactement de 3840X1080 pixels et dans l'un des formats suivants : jpg, jpeg, png et bmp. Si votre organisation veut utiliser une image personnalisée, le concepteur graphique trouvera le [modèle Photoshop de thème personnalisé](https://go.microsoft.com/fwlink/?linkid=870441) utile. Il contient des détails supplémentaires sur l’endroit où placer divers éléments dans une image de thème et les zones qui apparaissent dans les consoles et les affichages.
  
Le fichier de configuration XML doit être mis à jour lors du démarrage de l'appareil pour reconnaître l'image du thème. Lorsque le nouveau fichier XML est traité et supprimé, le fichier graphique de thème est supprimé de l’annuaire.
  
## <a name="see-also"></a>Voir aussi


[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)

[Configurer un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
