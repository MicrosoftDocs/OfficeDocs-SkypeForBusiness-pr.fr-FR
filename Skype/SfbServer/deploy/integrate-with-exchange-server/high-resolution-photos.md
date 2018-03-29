---
title: Configuration de l’utilisation de photos haute résolution dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Résumé : Configurer l’utilisation de photos haute résolution dans 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 9d5117f2774a928e520aa211007fffb0740a2b52
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server-2015"></a>Configuration de l’utilisation de photos haute résolution dans Skype Entreprise Server 2015
 
**Résumé :** Configurer l’utilisation de photos haute résolution dans 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.
  
Dans Skype pour Business Server 2015 photos peuvent être stockées dans les lettres d’un utilisateur de 2016 d’Exchange Server ou Exchange Server 2013, qui permet de la taille de la photo jusqu'à 648 pixels 648 pixels. En outre, Exchange Server peut redimensionner automatiquement ces photos à utiliser dans les différents produits selon les besoins. Cela donne généralement trois tailles et résolutions de photos différentes :
  
- 64 x 64 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous téléchargez des photos dans Exchange Server, Exchange va automatiquement créer un pixel 64 par version 64 pixels de cette photo et mettre à jour l’attribut l’utilisateur thumbnailPhoto. Notez toutefois que l’inverse n’est pas true : Si vous mettez manuellement à jour l’attribut thumbnailPhoto dans Active Directory la photo dans la boîte aux lettres Exchange de l’utilisateur n'est pas automatiquement actualisée.
    
- 96 x 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype pour Business Web App et Skype pour les entreprises.
    
- 648 pixels par 648 pixels pour les utilisent dans Skype pour les entreprises et Skype pour Business Web App Skype pour Business Web App.
    
> [!NOTE]
> Si vous disposez des ressources, il est recommandé que vous téléchargez des photos de 648 x 648 ; qui fournit la résolution maximale et une qualité d’image optimale dans toutes les applications Office 2013. Chaque photo JPEG avec une taille de 648 x 648 et une profondeur de 24 bits des résultats dans un fichier de taille d’environ 240 kilo-octets. Chaque photo JPEG de 648 x 648 pixels et d’une profondeur de 24 bits équivaut à une taille de fichier d’environ 240 kilo-octets, ce qui signifie que vous avez besoin d’environ 1 mégaoctet d’espace disque pour quatre photos d’utilisateurs. 
  
Photos haute résolution, qui sont accessibles à l’aide des Services Web Exchange, peuvent être téléchargés par les utilisateurs qui exécutent Outlook 2013 Web App ; les utilisateurs ne sont autorisés à mettre à jour de leur propre photo. Les administrateurs, cependant, peuvent mettre à jour la photo pour n’importe quel utilisateur à l’aide d’Exchange Management Shell et une série de commandes de Windows PowerShell semblables à la suivante :
  
```
$photo = ([Byte ] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

La première commande de l’exemple ci-dessus utilise l’applet de commande Get-Content pour lire le contenu du fichier C:\Photos\Kenmyer.jpg et stocker les données dans une variable nommée Preview$photo. Dans la deuxième commande, l’applet de commande Set-UserPhoto des Exchange permet de télécharger la photo et joindre cette photo pour le compte d’utilisateur de Myer.
  
> [!NOTE]
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur au moyen d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. Consultez la documentation de l’applet de commande Set-UserPhoto à [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) pour plus d’informations
  
Télécharger la photo n’équivaut pas à l’assigner au compte d’utilisateur de Ken Myer. Cela entraîne simplement l’affichage d’un aperçu de cette photo dans la page Options d’Outlook Web App. Pour assigner cette photo au compte d’utilisateur, celui-ci doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour assigner la photo au compte d’utilisateur de Ken Myer :
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut ouvrir une session Skype entreprise, sélectionnez les **Options**et puis sélectionnez **Mon image**. La photo nouvellement téléchargée doit alors s’afficher comme photo personnelle de Ken. En guise d’alternative, les administrateurs peuvent vérifier la photo de tout utilisateur en lançant Internet Explorer et en accédant à une URL semblable à la suivante :
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si l’administrateur peut visualiser la photo à l’aide d’Internet Explorer, mais l’utilisateur ne peut pas afficher la photo de son dans Skype pour entreprise il peut y avoir un problème de connectivité avec les Services Web Exchange ou avec le service de découverte automatique d’Exchange.
  
Notez qu’aucune configuration supplémentaire n’est nécessaire pour rendre cette photo disponible dans Skype pour les entreprises. À la place, la photo sera instantanément disponible une fois qu’elle a été téléchargée et que l’applet de commande Set-UserPhoto a été exécuté.
  

