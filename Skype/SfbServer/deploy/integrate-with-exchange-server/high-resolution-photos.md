---
title: Configurer l’utilisation de photos haute résolution dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Résumé : Configurez l’utilisation de photos haute résolution dans Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.'
ms.openlocfilehash: 1d631fb8ec8f17bb883f59936bb6e4adbeb02395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894322"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurer l’utilisation de photos haute résolution dans Skype pour Business Server
 
**Résumé :** Configurer l’utilisation de photos haute résolution dans Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.
  
Dans Skype pour Business Server photos peuvent être stockées dans Exchange Server 2016 ou Exchange Server 2013 boîte aux lettres un utilisateur, qui permet à des tailles de photo jusqu'à 648 x 648 pixels. En outre, Exchange Server se redimensionne automatiquement les photos à utiliser dans les différents produits selon vos besoins. Cela donne généralement trois tailles et résolutions de photos différentes :
  
- 64 x 64 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous téléchargez des photos dans Exchange Server, Exchange automatiquement créer un pixel 64 en version 64 pixels de cette photo et l’attribut thumbnailPhoto de l’utilisateur de mettre à jour. Toutefois, notez que l’inverse n’est pas vrai : Si vous mettez à jour l’attribut thumbnailPhoto dans Active Directory manuellement la photo dans la boîte aux lettres Exchange pas automatiquement à jour.
    
- 96 x 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype pour l’application Web de gestion et Skype pour les entreprises.
    
- 648 x 648 pixels, pour utilisent dans Skype pour les entreprises et Skype pour Business Web application Skype pour Business Web App.
    
> [!NOTE]
> Si vous disposez des ressources, il est recommandé que vous téléchargez des photos 648 x 648 ; qui fournit la résolution maximale et une qualité optimale de l’image dans toutes les applications Office 2013. Chaque photo JPEG avec une taille de 648 x 648 et une profondeur de 24 bits génère une taille de fichier d’environ 240 kilo-octets. Chaque photo JPEG de 648 x 648 pixels et d’une profondeur de 24 bits équivaut à une taille de fichier d’environ 240 kilo-octets, ce qui signifie que vous avez besoin d’environ 1 mégaoctet d’espace disque pour quatre photos d’utilisateurs. 
  
Photos haute résolution, qui sont accessibles à l’aide des Services Web Exchange, peuvent être téléchargés par les utilisateurs qui exécutent Outlook 2013 Web App ; les utilisateurs sont autorisés uniquement pour mettre à jour leur propre photo. Administrateurs, cependant, peuvent mettre à jour la photo d’un utilisateur à l’aide de l’environnement Exchange Management Shell et une série de commandes Windows PowerShell semblables au suivant :
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

La première commande dans l’exemple précédent utilise le `Get-Content` applet de commande pour lire le contenu du fichier C:\Photos\Kenmyer.jpg et stockez ces données dans une variable nommée $photo. Dans la deuxième commande, l’applet de commande Exchange `Set-UserPhoto` est utilisée pour charger la photo et joindre cette photo au compte d’utilisateur Ken Myer.
  
> [!NOTE]
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur au moyen d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. Consultez la documentation de l’applet de commande Set-UserPhoto à [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) pour plus d’informations
  
Télécharger la photo n’équivaut pas à l’assigner au compte d’utilisateur de Ken Myer. Cela entraîne simplement l’affichage d’un aperçu de cette photo dans la page Options d’Outlook Web App. Pour assigner cette photo au compte d’utilisateur, celui-ci doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour assigner la photo au compte d’utilisateur de Ken Myer :
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut se connecter à Skype pour l’entreprise, sélectionnez les **Options**et sélectionnez **Mon image**. La photo nouvellement téléchargée doit alors s’afficher comme photo personnelle de Ken. En guise d’alternative, les administrateurs peuvent vérifier la photo de tout utilisateur en lançant Internet Explorer et en accédant à une URL semblable à la suivante :
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si l’administrateur peut afficher les photos à l’aide d’Internet Explorer, mais l’utilisateur ne peut pas afficher sa photo dans Skype pour les entreprises peuvent poser un problème de connectivité avec les Services Web Exchange ou le service de découverte automatique Exchange.
  
Notez également qu’aucune configuration supplémentaire n’est nécessaire afin de rendre cette photo disponible sur Skype pour les entreprises. Au lieu de cela, la photo sera disponible immédiatement après qu’il a été téléchargé et `Set-UserPhoto` applet de commande a été exécutée.
