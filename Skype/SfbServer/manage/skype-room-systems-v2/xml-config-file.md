---
title: Gestion à distance des paramètres d'une console Skype Room Systems v2 à l'aide d'un fichier de configuration XML
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: Cet article traite de la gestion à distance des paramètres par défaut utilisés par un périphérique de v2 Skype salle systèmes, y compris l’application d’un thème personnalisé.
ms.openlocfilehash: 14891401c8cd13f35879ea064f2be49f88b1c68a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>Gestion à distance des paramètres d'une console Skype Room Systems v2 à l'aide d'un fichier de configuration XML
 
Cet article traite de la gestion à distance des paramètres par défaut utilisés par un périphérique de v2 Skype salle systèmes, y compris l’application d’un thème personnalisé.
  
En modifiant un fichier XML maître et en envoyant des copies aux consoles que vous gérez, vous pouvez modifier les paramètres par défaut des appareils gérés à distance. Cet article explique comment créer ce type de fichier et fournit des liens vers des discussions indiquant comment les placer selon vos besoins sur les appareils gérés à distance. À l’aide de cette méthode, vous pouvez également implémenter des thèmes personnalisés sur vos consoles v2 de systèmes de salle de Skype. 
  
## <a name="creating-an-xml-configuration-file"></a>Création d'un fichier de configuration XML

Le tableau ci-dessous explique les éléments affichés dans cet exemple, SkypeSettings.xml (il s’agit d’un nom de fichier requis) fichier de configuration. 
  
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
             <AutoRotatePassword>1</AutoRotatePassword>
  </UserAccount>    
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

Si le fichier XML est formé de manière incorrecte (le type d'une valeur de variable est incorrect, des éléments ne sont pas dans l'ordre correct, des éléments sont non fermés, etc.), les éléments jusqu'au point où l'erreur est détectée sont appliqués, puis le reste du fichier est ignoré lors du traitement. Tous les éléments inconnus dans le fichier XML sont ignorés. Si un paramètre est omis, il reste inchangé sur l'appareil. Si la valeur d’un paramètre n’est pas valide, sa valeur précédente reste inchangée.
  
**Éléments XML**
 
|**Élément**|**Type de**|**Niveau**|**Utilisation de**|
|:-----|:-----|:-----|:-----|
|\<SkypeSettings\>  <br/> |Conteneur de tous les éléments.  <br/> ||Obligatoire.  <br/> |
| \<AutoScreenShare\> <br/> |Valeur booléenne & #x 2777 ; <br/> |Première & #x 2776 ; <br/> |   Si ce paramètre est vrai, le partage d'écran automatique est activé. <br/> |
|\<HideMeetingName\>  <br/> |Valeur booléenne & #x 2777 ; <br/> |Première & #x 2776 ; <br/> |Si ce paramètre est vrai, les noms de réunion sont masqués.  <br/> |
|\<Compte_utilisateur\>  <br/> |Conteneur  <br/> |Première & #x 2776 ; <br/> |Conteneur des paramètres d'identification.  <br/> L'adresse de connexion, l'adresse d'Exchange ou l'adresse de messagerie est généralement identique, comme par exemple RanierConf@contoso.com.   <br/> |
|\<SkypeMeetingsEnabled\>  <br/> |Valeur booléenne & #x 2777 ; <br/> |Première & #x 2776 ; <br/> |Cette fonctionnalité est activée par défaut.  <br/> |
|\<TeamsMeetingsEnabled\>  <br/> |Valeur booléenne & #x 2777 ; <br/> |Première & #x 2776 ; <br/> |Cette fonctionnalité est désactivée par défaut.  <br/> Le fichier XML est considéré comme incorrect si les deux \<SkypeMeetingsEnabled\> et\<TeamsMeetingsEnabled\> sont désactivés, mais il est acceptable d’avoir les deux paramètres sont activés en même temps.  <br/> |
|\<SkypeSignInAddress\>  <br/> |Chaîne 3 <br/> ||Nom de connexion au compte d'appareil Skype Entreprise de la console.  <br/> |
|\<ExchangeAddress\>  <br/> |Chaîne 3 <br/> ||Nom de connexion au compte d'appareil Exchange de la console.  <br/> Si l'adresse d'Exchange est omise, l'adresse de connexion à Skype ne sera pas réutilisée automatiquement.   <br/> |
|\<DomainUsername\>  <br/> |Chaîne & #x 2778 ; <br/> ||Nom de domaine et d'utilisateur de la console, par exemple Seattle\RanierConf.  <br/> |
|\<Mot de passe\>  <br/> |Chaîne 3 <br/> ||  Le paramètre du mot de passe est le même mot de passe que celui utilisé pour la connexion au compte d'appareil Skype Entreprise.  <br/> |
| \<ConfigureDomain\> <br/> |Chaîne & #x 2778 ; <br/> ||Vous pouvez répertorier plusieurs domaines, séparés par des virgules.  <br/> |
|\<AutoRotatePassword\>  <br/> |Valeur booléenne & #x 2777 ; <br/> |||
| \<DualScreenMode\> <br/> |Valeur booléenne & #x 2777 ; <br/> |Première & #x 2776 ; <br/> |Si la valeur est true, le mode double écran est activé. Dans le cas contraire, l'appareil utilisera le mode d'écran unique.  <br/> |
|\<SendLogs\>  <br/> |Conteneur  <br/> |Première & #x 2776 ; <br/> ||
|\<EmailAddressForLogsAndFeedback\>  <br/> |Chaîne & #x 2778 ; <br/> ||Ce paramètre définit une adresse électronique en option à laquelle les journaux peuvent être envoyés lorsque la fenêtre "Envoyer des commentaires" s'affiche.   <br/> |
|\<SendLogsAndFeedback\>  <br/> |Valeur booléenne & #x 2777 ; <br/> ||  Si ce paramètre est vrai, les journaux sont envoyés à l'administrateur. Si ce paramètre est faux, seuls les commentaires sont envoyés à l'administrateur (pas les journaux). <br/> |
| \<Périphériques\> <br/> |Conteneur  <br/> |Première & #x 2776 ; <br/> | Les noms des appareils audio connectés dans les éléments enfants sont les mêmes valeurs que celles qui sont répertoriées dans l'application du gestionnaire de périphériques. La configuration peut contenir un appareil qui n'existe pas actuellement sur le système, tel qu'un périphérique audio/vidéo qui n'est pas connecté à la console actuellement. La configuration sera conservée pour l'appareil respectif. <br/> |
|\<MicrophoneForCommunication\>  <br/> |Chaîne 3 <br/> ||Définit le microphone qui sera utilisé comme appareil d'enregistrement dans une conférence.  <br/> |
|\<SpeakerForCommunication\>  <br/> |Chaîne 3 <br/> ||Périphérique qui sera utilisé comme haut-parleur pour la conférence. Ce paramètre permet de définir le haut-parleur qui sera utilisé pour entendre le son lors d'un appel.  <br/> |
|\<DefaultSpeaker\>  <br/> |Chaîne 3 <br/> ||Périphérique qui sera utilisé pour lire le son d'une source de réception HDMI.   <br/> |
| \<Utilisation des thèmes\> <br/> |Conteneur  <br/> |Première & #x 2776 ; <br/> |Une des fonctionnalités qui peuvent être appliquées en utilisant un fichier XML est un thème personnalisé pour votre organisation. Vous ne pourrez pas spécifier un nom de thème, une image d’arrière-plan et une couleur.  <br/> |
|\<ThemeName\>  <br/> |Chaîne & #x 2778 ; <br/> || Permet d'identifier le thème sur le client. Les options pour le nom du thème sont Par défaut, un des thèmes prédéfinis fournis ou Personnalisé. <br/>  Les noms de thème personnalisé doivent toujours utiliser le nom *personnalisé* . L';interface utilisateur du client peut être définie sur la console sur Par défaut ou l';un des thèmes prédéfinis, mais l';application d';un thème personnalisé doit être définie à distance par Administrateur. <br/>  Les thèmes prédéfinis sont les suivants :  <br/>  Par défaut <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  Pour désactiver le thème en cours, utilisez « Aucun thème » pour le ThemeName. <br/> |
|\<CustomThemeImageUrl\>  <br/> |Chaîne & #x 2778 ; <br/> ||Requis si vous utilisez un thème personnalisé, sinon facultatif. Voir la section [Images de thème personnalisé](xml-config-file.md#Themes) ci-dessous pour plus de détails sur l’image de thème personnalisé. <br/> |
|\<CustomThemeColor\>  <br/> |Conteneur  <br/> ||Conteneur pour le \<RedComponent\>, \<GreenComponent\>, et \<BlueComponent\> valeurs. Ces valeurs sont obligatoires si un thème personnalisé est utilisé.  <br/> |
|\<RedComponent\>  <br/> |Octet (0-255)  <br/> ||Représente le composant de la couleur rouge.  <br/> |
|\<GreenComponent\>  <br/> |Octet (0-255)  <br/> ||Représente le composant de la couleur verte.  <br/> |
|\<BlueComponent\>  <br/> |Octet (0-255)  <br/> ||Représente le composant de la couleur bleue.  <br/> |
   
& #x 2776 ; Tous les éléments de premier niveau sont facultatifs. Si un élément du premier niveau est omis, tous ses paramètres enfants restent inchangés sur l';appareil.
  
& #x 2777 ; Un indicateur boolean peut être une des opérations suivantes : true, false, 0 ou 1. Des valeurs booléennes ou numériques laissées vides peuvent rendre le fichier XML incorrect, et les paramètres ne seront donc pas modifiés.
  
 & #x 2778 ; Si un paramètre de chaîne est présente, vide et vide est une valeur valide, le paramètre est désactivé sur le périphérique.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Gestion des paramètres de la console à l'aide d'un fichier de configuration XML

Au démarrage, si une console v2 de systèmes de salle Skype détecte un fichier XML nommé SkypeSettings.xml à l’emplacement ** C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, elle appliquera les paramètres de configuration indiqués par le fichier XML, puis supprimez le fichier XML.
  
En fonction des périphériques de v2 Skype salle systèmes combien votre entreprise a et la façon dont vous choisissez de gérer leur configuration, il existe un certain nombre de façons de placer le fichier de configuration XML. Une fois le fichier poussé sur la console, redémarrez-la pour traiter les modifications apportées à la configuration. Le fichier de configuration XML est supprimé une fois qu';il a été traité. Décrit les méthodes de gestion proposées pour les périphériques de systèmes de salle Skype v2 :
  
- [Configuration de la stratégie de groupe pour Skype Room Systems v2](skype-room-systems-v2.md#GroupPolicy)
    
- [Configurer un élément de fichier](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx) et [gestion à distance à l’aide de PowerShell](skype-room-systems-v2.md#RemotePS)
    
Vous pouvez utiliser la méthode que vous souhaitez tant que vous pouvez l'utiliser pour transférer des fichiers et déclencher un redémarrage sur la console. Le fichier doit être lisible et accessible en écriture-capable de supprimer par compte d’utilisateur local du périphérique (de préférence, il doit être possédé par et disposent de privilèges complets accordés à cet utilisateur). Si les autorisations du fichier ne sont pas définies correctement, le logiciel risque de ne pas pouvoir appliquer les paramètres après le traitement réussi de celui-ci et éventuellement se bloquer.
  
## <a name="custom-theme-images"></a>Personnaliser les images du thème
<a name="Themes"> </a>

Le fichier d’image de thème personnalisé doit être placé dans **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, saisissez le nom de fichier et l’extension de la <CustomThemeImageUrl> variable.
  
Le fichier image doit être exactement de 3840X1080 pixels et dans l'un des formats suivants : jpg, jpeg, png et bmp. Si votre organisation souhaite une image personnalisée, un concepteur graphique utiles notre [Modèle de Photoshop de thème personnalisé](https://go.microsoft.com/fwlink/?linkid=870441) . Il contient plus en détail sur où placer les différents éléments d’une image de thème et les zones qui apparaissent sur les consoles et les affiche.
  
Le fichier de configuration XML doit être mis à jour lors du démarrage de l'appareil pour reconnaître l'image du thème. Lorsque le nouveau fichier XML a été traité et supprimé, le fichier graphique du thème est supprimé du répertoire.
  
## <a name="see-also"></a>Voir aussi
<a name="Themes"> </a>

#### 

[Gérer l’espace de Skype systèmes v2](skype-room-systems-v2.md)
#### 

[Configurer un élément de fichier](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)

