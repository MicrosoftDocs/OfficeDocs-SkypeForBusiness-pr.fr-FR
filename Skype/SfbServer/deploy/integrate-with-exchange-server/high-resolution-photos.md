---
title: Configurer l’utilisation de photos haute résolution dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Résumé : Configurez l’utilisation des photos haute résolution dans Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online et Skype Entreprise Server.'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834004"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurer l’utilisation de photos haute résolution dans Skype Entreprise Server
 
**Résumé :** Configurez l’utilisation des photos haute résolution dans Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online et Skype Entreprise Server.
  
Dans Skype Entreprise Server, les photos peuvent être stockées dans la boîte aux lettres Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 ou Exchange Online d’un utilisateur, ce qui permet des tailles de photos de 648 pixels par 648 pixels. En outre, Exchange Server pouvez resize automatiquement ces photos pour les utiliser dans différents produits selon vos besoins. Cela signifie généralement trois tailles et résolutions de photos différentes :
  
- 64 pixels par 64 pixels, taille utilisée pour l’attribut ThumbnailPhoto Active Directory. Si vous téléchargez une photo sur Exchange Server, Exchange crée automatiquement une version de 64 pixels sur 64 pixels de cette photo et met à jour l’attribut thumbnailPhoto de l’utilisateur. Notez toutefois que l’inverse n’est pas vrai : si vous mettez manuellement à jour l’attribut thumbnailPhoto dans Active Directory, la photo dans la boîte aux lettres Exchange de l’utilisateur ne sera pas automatiquement mise à jour.
    
- 96 pixels par 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype Entreprise Web App et Skype Entreprise.
    
- 648 pixels par 648 pixels pour une utilisation dans Skype Entreprise et Skype Entreprise Web App Skype Entreprise Web App.
    
> [!NOTE]
> Si vous disposez des ressources, nous vous recommandons de charger 648 x 648 photos . qui fournit la résolution maximale et une qualité d’image optimale dans n’importe quelle application Office 2013. Chaque photo JPEG d’une taille de 648 x 648 et d’une profondeur de 24 bits entraîne une taille de fichier d’environ 240 kilo-octets. Cela signifie que vous aurez besoin d’environ 1 mégaoctet d’espace disque pour 4 photos utilisateur. 
  
Les photos haute résolution, accessibles à l’aide des services web Exchange, peuvent être téléchargées par les utilisateurs qui exécutent Outlook 2013 Web App. les utilisateurs sont uniquement autorisés à mettre à jour leur propre photo. Les administrateurs, toutefois, peuvent mettre à jour la photo pour n’importe quel utilisateur à l’aide de l’Exchange Management Shell et d’une série de commandes Windows PowerShell semblables à ce qui suit :
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

La première commande de l’exemple précédent utilise la cmdlet pour lire le contenu du fichier C:\Photos\Kenmyer.jpg et stocker ces données dans une variable nommée `Get-Content` $photo. Dans la deuxième commande, la cmdlet Exchange est utilisée pour télécharger la photo et `Set-UserPhoto` l’attacher au compte d’utilisateur de Ken Myer.
  
> [!NOTE]
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également référencer un compte d’utilisateur à l’aide d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. Pour plus d’informations, voir la documentation Set-UserPhoto cmdlet [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)
  
Le téléchargement de la photo n’équivaut pas à affecter cette photo au compte d’utilisateur de Ken Myer. Au lieu de cela, le téléchargement de la photo entraîne simplement un aperçu de cette photo à afficher sur la page Options d’Outlook Web App. Pour affecter réellement cette photo au compte  d’utilisateur, l’utilisateur doit cliquer sur Enregistrer dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour affecter la photo au compte d’utilisateur de Ken Myer :
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut se connecter à Skype Entreprise, sélectionner **Options,** puis **Ma photo**. La photo nouvellement téléchargée doit être affichée en tant que photo personnelle de Ken. Les administrateurs peuvent également vérifier la photo de n’importe quel utilisateur en démarrage d’Internet Explorer et en naviguant vers une URL semblable à celle-ci :
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Si l’administrateur peut afficher la photo à l’aide d’Internet Explorer, mais que l’utilisateur ne peut pas afficher sa photo dans Skype Entreprise, il peut y avoir un problème de connectivité avec les services web Exchange ou avec le service de découverte automatique Exchange.
  
Notez également qu’aucune configuration supplémentaire n’est requise pour rendre cette photo disponible dans Skype Entreprise. Au lieu de cela, la photo sera immédiatement disponible une fois qu’elle a été téléchargée et que la `Set-UserPhoto` cmdlet a été exécuté.
