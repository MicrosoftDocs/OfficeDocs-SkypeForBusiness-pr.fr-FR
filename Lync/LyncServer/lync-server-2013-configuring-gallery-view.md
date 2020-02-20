---
title: 'Lync Server 2013 : configuration de la vue de la Galerie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configuration de la vue de la galerie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Dans Lync Server 2013, vous configurez la vidéoconférence d’affichage de galerie dans la stratégie de conférence. La vue Galerie est activée par défaut. Si vous ne souhaitez pas autoriser la vue Galerie ou si vous voulez l’autoriser pour certains utilisateurs seulement, vous devez désactiver la fonctionnalité dans la stratégie de conférence.

Lorsque la vidéo d’un participant à la Conférence n’est pas disponible, l’expérience de visualisation de la Galerie des utilisateurs peut être améliorée si vous déployez des photos haute résolution, une nouvelle fonctionnalité de Lync Server 2013. Les photos haute résolution offrent une alternative aux petites photos de contact de résolution limitée stockées dans les services de domaine Active Directory. Les photos haute résolution sont stockées dans la boîte aux lettres Exchange 2013 d’un utilisateur et, par conséquent, vous devez intégrer Lync Server 2013 à Exchange 2013. Pour plus d’informations, reportez-vous à l’article du blog NextHop, « intégration d' [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)Exchange 2013 et de Lync Server 2013 », à l’adresse.

<div>


> [!NOTE]  
> Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.



</div>

Vous pouvez afficher ou modifier les paramètres d’affichage de la galerie à l’aide du panneau de configuration Lync Server 2013 ou de l’une des applets de commande suivantes :

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurez la vue Galerie à l’aide des paramètres de stratégie de conférence suivants :

  - **AllowMultiview**   ce paramètre détermine si un utilisateur est autorisé à organiser les conférences vidéo de la Galerie. Ce paramètre s’applique aux réunions planifiées et ad hoc créées par l’utilisateur.
    
    Exemples :
    
      - Ce paramètre est défini sur true pour l’utilisateur A, qui est hébergé sur un pool Lync Server 2013. Les réunions organisées par l’utilisateur A permettent aux utilisateurs d’envoyer et de recevoir plusieurs flux vidéo.
    
      - Ce paramètre est défini sur false pour l’utilisateur B, qui est hébergé sur un pool Lync Server 2013. Les réunions organisées par l’utilisateur B ont un flux vidéo unique semblable à l’expérience de vidéoconférence fournie par Lync Server 2010.
    
    Ce paramètre détermine quelles sont les personnes qui peuvent organiser des réunions autorisant plusieurs flux vidéo. Les participants aux réunions qui autorisent plusieurs flux vidéo peuvent être autorisés ou non à recevoir plusieurs flux vidéo, en fonction de leurs autorisations individuelles (voir la description du paramètre EnableMultiviewJoin).

  - **EnableMultiviewJoin**   ce paramètre contrôle si un participant à une réunion reçoit l’expérience vidéo en mode Galerie dans les réunions qui l’autorisent. Ce paramètre contrôle l’expérience de l’utilisateur dans les réunions auxquelles il participe.
    
    Exemples :
    
      - Ce paramètre est défini sur true pour l’utilisateur C. l’utilisateur C peut recevoir plusieurs flux vidéo lorsqu’il participe à une réunion organisée ou démarrée par l’utilisateur A. l’utilisateur C reçoit un seul flux vidéo semblable à l’expérience de vidéoconférence fournie par Lync Server 2010. participation à une réunion organisée ou démarrée par l’utilisateur B.
    
      - Ce paramètre est défini sur false pour l’utilisateur D. User D reçoit un flux vidéo unique semblable à l’expérience de vidéoconférence fournie par Lync Server 2010 lorsqu’il participe à une réunion organisée par l’utilisateur A ou l’utilisateur B.

La procédure suivante est un exemple d’utilisation de Lync Server Management Shell pour activer la conférence vidéo sur les vues de la Galerie.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Pour modifier la stratégie de conférence de la visioconférence dans la vue Galerie

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

