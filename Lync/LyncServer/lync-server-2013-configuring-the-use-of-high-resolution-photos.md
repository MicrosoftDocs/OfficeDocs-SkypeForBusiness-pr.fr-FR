---
title: 'Lync Server 2013 : configuration de l’utilisation de photos haute résolution'
description: 'Lync Server 2013 : configuration de l’utilisation de photos haute résolution.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b0077fbfe2d525a7dac651ebd4c2a95892d3d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544170"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Microsoft Lync Server 2010 offre aux utilisateurs la possibilité d’afficher des photos de leurs contacts (et de mettre à la disposition de leurs propres photos). En règle générale, ces photos ont été stockées dans le cadre de l’attribut thumbnailPhoto de l’utilisateur dans Active Directory. Cela a permis de limiter sérieusement la taille et la résolution des photos : l’attribut thumbnailPhoto ne peut contenir qu’une photographie d’une taille maximale de 48 pixels par 48 pixels.

Dans Microsoft Lync Server 2013, toutefois, les photos peuvent être stockées dans la boîte aux lettres 2013 de Microsoft Exchange Server d’un utilisateur ; Cela permet d’obtenir des photos d’une taille de 648 x 648 pixels. En outre, Exchange 2013 peut redimensionner automatiquement ces photos afin de les utiliser dans différents produits selon vos besoins. En règle générale, cela signifie trois tailles et résolutions de photos différentes :

  - 48 pixels par 48 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous téléchargez une photo vers Exchange 2013, Exchange crée automatiquement une version de 48 pixel par 48 pixel de cette photo et met à jour l’attribut thumbnailPhoto de l’utilisateur. Notez toutefois que l’inverse n’est pas vrai : Si vous mettez à jour manuellement l’attribut thumbnailPhoto dans Active Directory, la photo dans la boîte aux lettres Exchange 2013 de l’utilisateur ne sera pas automatiquement mise à jour.

  - 96 pixels par 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App et Lync 2013.

  - 648 pixels par 648 pixels pour une utilisation dans Lync 2013 et Microsoft Lync Web App.

<div>


> [!NOTE]  
> Si vous disposez des ressources, il est recommandé de télécharger des photos 648 x 648 ; Cela garantit une résolution maximale et une qualité d’image optimale dans n’importe quelle application Office 2013. Chaque photo JPEG avec une taille de 648 x 648 et une profondeur de 24 bits aboutit à une taille de fichier d’environ 240 kilo-octets. Cela signifie que vous aurez besoin d’environ 1 Mo d’espace disque pour chaque photo d’utilisateur de 4.



</div>

Les photos haute résolution, accessibles via les services Web Exchange, peuvent être téléchargées par les utilisateurs qui exécutent Outlook 2013 Web App ; les utilisateurs ne sont autorisés qu’à mettre à jour leur propre photo. Toutefois, les administrateurs peuvent mettre à jour la photo de n’importe quel utilisateur en utilisant l’environnement de commande Exchange Management Shell et une série de commandes Windows PowerShell semblables à ce qui suit :

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

La première commande de l’exemple précédent utilise la cmdlet Get-Content pour lire le contenu du fichier C : \\ Photos \\Kenmyer.jpg et stocker ces données dans une variable nommée $photo. Dans la seconde commande, l’applet de commande Exchange Set-UserPhoto est utilisée pour télécharger la photo et la joindre au compte d’utilisateur de Ken Myer.

<div>


> [!NOTE]  
> Dans cet exemple, le nom d’affichage Active Directory de Ken Myer est utilisé comme identité du compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur à l’aide d’autres identificateurs, tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. Pour plus d’informations, reportez-vous à la documentation de l’applet de commande Set-UserPhoto. <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>



</div>

Le téléchargement de la photo n’équivaut pas à l’affectation de cette photo au compte d’utilisateur de Ken Myer. Au lieu de cela, le téléchargement de la photo entraîne simplement l’affichage d’un aperçu de cette photo sur la page Options d’Outlook Web App. Pour affecter réellement cette photo au compte d’utilisateur, l’utilisateur doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour affecter la photo au compte d’utilisateur de Ken Myer :

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut se connecter à Lync 2013, sélectionner des **options**, puis sélectionner **mon image**. La photo téléchargée est affichée sous la forme photo personnelle de Ken. Par ailleurs, les administrateurs peuvent vérifier la photo de n’importe quel utilisateur en démarrant Internet Explorer et en accédant à une URL semblable à celle-ci :

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Si l’administrateur peut afficher la photo à l’aide d’Internet Explorer, mais que l’utilisateur ne peut pas afficher sa photo dans Lync 2013, cela indique généralement un problème de connectivité avec les services Web Exchange ou avec le service de découverte automatique Exchange.

Notez également qu’aucune configuration supplémentaire n’est requise pour que cette photo soit disponible dans Lync 2013. Au lieu de cela, la photo est immédiatement disponible une fois qu’elle a été téléchargée et que la cmdlet Set-UserPhoto a été exécutée.

</div>

<span> </span>

</div>

</div>

</div>

