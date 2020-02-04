---
title: 'Lync Server 2013 : configuration de l’utilisation de photos haute résolution'
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
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Microsoft Lync Server 2010 offre la possibilité aux utilisateurs d’afficher des photos de leurs contacts (et de rendre leurs propres photos accessibles à d’autres personnes). Ces photos sont généralement stockées dans le cadre de l’attribut thumbnailPhoto de l’utilisateur dans Active Directory. Après avoir placé une limitation sérieuse quant à la taille et à la résolution des photos, l’attribut thumbnailPhoto ne peut contenir qu’une photo dont la taille maximale est de 48 pixels par 48 pixels.

Dans Microsoft Lync Server 2013, toutefois, les photos peuvent être stockées dans la boîte aux lettres 2013 du serveur Microsoft Exchange Server d’un utilisateur. Cela permet de redimensionner une photo de 648 pixels par 648 pixels. Par ailleurs, Exchange 2013 permet de redimensionner automatiquement ces photos pour une utilisation dans différents produits selon vos besoins. Cela donne généralement trois tailles et résolutions de photos différentes :

  - 48 pixels par 48 pixels, taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous chargez une photo dans Exchange 2013, Exchange créera automatiquement une version 48 pixels par 48 pixels de cette photo et mettre à jour l’attribut thumbnailPhoto de l’utilisateur. Notez, toutefois, que l’inverse n’est pas vrai : Si vous effectuez manuellement la mise à jour de l’attribut thumbnailPhoto dans Active Directory, la photo de la boîte aux lettres Exchange 2013 de l’utilisateur ne sera pas automatiquement mise à jour.

  - 96 pixels par 96 pixels pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App et Lync 2013.

  - 648 pixels par 648 pixels pour une utilisation dans Lync 2013 et Microsoft Lync Web App.

<div>


> [!NOTE]  
> Si vous disposez des ressources nécessaires, nous vous recommandons de télécharger des photos de 648 x 648 pixels. Cela permet de bénéficier de la résolution maximale et d’une qualité d’image optimale dans toutes les applications Office 2013. Chaque photo JPEG de 648 x 648 pixels et d’une profondeur de 24 bits équivaut à une taille de fichier d’environ 240 kilo-octets, ce qui signifie que vous avez besoin d’environ 1 mégaoctet d’espace disque pour quatre photos d’utilisateurs.



</div>

Les photos haute résolution, qui sont accessibles à l’aide des services Web Exchange, peuvent être chargées par les utilisateurs exécutant Outlook 2013 Web App ; les utilisateurs ne peuvent mettre à jour qu’une seule photo. En revanche, les administrateurs peuvent mettre à jour la photo de n’importe quel utilisateur à l’aide d’Exchange Management Shell et d’une série de commandes Windows PowerShell similaires à ce qui suit :

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

La première commande de l’exemple précédent utilise l’applet de commande Get-Content pour lire le contenu du fichier C\\:\\photos kenmyer. jpg et stocke ces données dans une variable nommée $photo. Dans la deuxième commande, l’applet de commande Exchange Set-UserPhoto est utilisée pour télécharger la photo et joindre cette photo au compte d’utilisateur de Ken Myer.

<div>


> [!NOTE]  
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur au moyen d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> Pour plus d’informations, voir la documentation relative à l’applet de UserPhoto Set-.



</div>

Télécharger la photo n’équivaut pas à l’assigner au compte d’utilisateur de Ken Myer. Cela entraîne simplement l’affichage d’un aperçu de cette photo dans la page Options d’Outlook Web App. Pour assigner cette photo au compte d’utilisateur, celui-ci doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour assigner la photo au compte d’utilisateur de Ken Myer :

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut se connecter à Lync 2013, sélectionner des **options**, puis sélectionner **mon image**. La photo nouvellement téléchargée doit alors s’afficher comme photo personnelle de Ken. En guise d’alternative, les administrateurs peuvent vérifier la photo de tout utilisateur en lançant Internet Explorer et en accédant à une URL semblable à la suivante :

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Si l’administrateur peut voir la photo à l’aide d’Internet Explorer, mais que l’utilisateur ne peut pas voir sa photo dans Lync 2013, cela indique généralement un problème de connectivité avec les services Web Exchange ou le service de découverte automatique Exchange.

Notez qu’aucune configuration supplémentaire n’est nécessaire pour rendre cette photo disponible dans Lync 2013. À la place, la photo sera instantanément disponible une fois qu’elle a été téléchargée et que l’applet de commande Set-UserPhoto a été exécuté.

</div>

<span> </span>

</div>

</div>

</div>

