---
title: Configurer l’utilisation de photos haute résolution dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Résumé: configurez l’utilisation de photos haute résolution dans Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278205"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurer l’utilisation de photos haute résolution dans Skype entreprise Server
 
**Résumé:** Configurer l’utilisation de photos haute résolution dans Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.
  
Les photos de Skype entreprise Server peuvent être stockées dans une boîte aux lettres Exchange Server 2016 ou Exchange Server 2013, qui permet de mettre en photo des tailles de 648 648 pixels. Par ailleurs, Exchange Server peut redimensionner automatiquement ces photos pour une utilisation dans différents produits selon vos besoins. Cela donne généralement trois tailles et résolutions de photos différentes :
  
- 64 x 64 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous téléchargez une photo sur Exchange Server, Exchange crée automatiquement une version de 64 pixels par 64 pixels de cette photo et met à jour l’attribut thumbnailPhoto de l’utilisateur. Notez, toutefois, que l’inverse n’est pas vrai: Si vous effectuez manuellement la mise à jour de l’attribut thumbnailPhoto dans Active Directory, la photo de la boîte aux lettres Exchange de l’utilisateur ne sera pas automatiquement mise à jour.
    
- 96 pixels par 96 pixels pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype entreprise Web App et Skype entreprise.
    
- 648 pixels par 648 pixels pour une utilisation dans Skype entreprise et Skype entreprise Web App sur Skype entreprise Web App.
    
> [!NOTE]
> Si vous disposez des ressources, nous vous recommandons de télécharger 648 x 648 photos; Cela fournit une résolution maximale et une qualité d’image optimale dans n’importe quelle application Office 2013. Chaque photo JPEG d’une taille de 648 x 648 et une profondeur de 24 bits génère une taille de fichier d’environ 240 Ko. Chaque photo JPEG de 648 x 648 pixels et d’une profondeur de 24 bits équivaut à une taille de fichier d’environ 240 kilo-octets, ce qui signifie que vous avez besoin d’environ 1 mégaoctet d’espace disque pour quatre photos d’utilisateurs. 
  
Les photos haute résolution, qui sont accessibles à l’aide des services Web Exchange, peuvent être chargées par les utilisateurs exécutant Outlook 2013 Web App; les utilisateurs ne peuvent mettre à jour qu’une seule photo. En revanche, les administrateurs peuvent mettre à jour la photo de n’importe quel utilisateur à l’aide d’Exchange Management Shell et d’une série de commandes Windows PowerShell similaires à ce qui suit:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

La première commande de l’exemple précédent utilise l' `Get-Content` applet de commande pour lire le contenu du fichier C:\Photos\Kenmyer.jpg et stocker ces données dans une variable nommée $photo. Dans la deuxième commande, l’applet `Set-UserPhoto` de commande Exchange est utilisée pour télécharger la photo et la joindre à la personne du compte utilisateur de Ken Myer.
  
> [!NOTE]
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur au moyen d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Pour plus d’informations, voir la documentation relative à l’applet de UserPhoto Set-.
  
Télécharger la photo n’équivaut pas à l’assigner au compte d’utilisateur de Ken Myer. Cela entraîne simplement l’affichage d’un aperçu de cette photo dans la page Options d’Outlook Web App. Pour assigner cette photo au compte d’utilisateur, celui-ci doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour assigner la photo au compte d’utilisateur de Ken Myer :
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Pour vérifier que la nouvelle photo a été affectée à un compte d’utilisateur, Ken Myer peut se connecter à Skype entreprise, sélectionner des **options**, puis sélectionner **mon image**. La photo nouvellement téléchargée doit alors s’afficher comme photo personnelle de Ken. En guise d’alternative, les administrateurs peuvent vérifier la photo de tout utilisateur en lançant Internet Explorer et en accédant à une URL semblable à la suivante :
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Si l’administrateur peut voir la photo à l’aide d’Internet Explorer, mais que l’utilisateur ne peut pas voir sa photo dans Skype entreprise, il existe peut-être un problème de connectivité avec les services Web Exchange ou le service de découverte automatique Exchange.
  
Notez qu’aucune configuration supplémentaire n’est nécessaire pour rendre cette photo disponible dans Skype entreprise. Au lieu de cela, la photo sera disponible instantanément après le téléchargement et l’applet de `Set-UserPhoto` la cmdlet a été exécutée.
