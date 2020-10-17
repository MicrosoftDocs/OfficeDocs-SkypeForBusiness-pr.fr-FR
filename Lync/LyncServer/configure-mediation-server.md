---
title: Configurer le serveur de médiation
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b5742d264efb8c84518511d40195a109594e2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503371"
---
# <a name="configure-mediation-server"></a>Configurer le serveur de médiation

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Cette procédure décrit en détail les étapes à suivre pour configurer le pool Lync Server 2013 afin qu’il utilise le serveur de médiation Lync Server 2013, au lieu du serveur de médiation Office Communications Server 2007 R2 hérité.

Pour réussir à publier, activer ou désactiver une topologie quand vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur. Pour plus d’informations, voir Déléguer des autorisations de configuration dans la documentation de déploiement consacrée aux serveurs Standard Edition ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.

<div>


> [!NOTE]  
> Pour obtenir les dernières informations sur la recherche de passerelles RTC qualifiées, de PBX IP et de services de jonction SIP fonctionnant avec Lync Server 2013, voir « Microsoft Unified Communications Open Interoperability Program » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Pour configurer le serveur de médiation à l’aide du Générateur de topologie

1.  Ouvrez une topologie existante à partir du Générateur de topologie.

2.  Dans le volet gauche, accédez à **Passerelles PSTN**.

3.  Cliquez avec le bouton droit sur **Passerelles PSTN**, puis cliquez sur **Nouvelle passerelle IP/PSTN**.

4.  Complétez la page **Définir une nouvelle passerelle IP/PSTN** à l’aide des informations suivantes :
    
      - Entrez le nom de domaine complet ou l’adresse IP de la passerelle. Le nom de domaine complet de la passerelle est requis si celle-ci utilise le protocole TLS.
    
      - Acceptez la valeur **Port d’écoute de la passerelle IP/PSTN** par défaut ou entrez le nouveau port d’écoute s’il a été modifié.
    
      - Définissez la valeur **Protocole de transport SIP**.

5.  Dans le volet gauche, accédez au **Pool frontal Enterprise Edition** ou au **Serveur Standard Edition**.

6.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

7.  Sous **Serveur de médiation**, définissez les **Ports d’écoute**.

8.  Ensuite, associez la nouvelle passerelle PSTN créée en la sélectionnant, puis en cliquant sur **Ajouter**.

9.  Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur **Lync Server**.

10. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

11. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

<div>


> [!NOTE]  
> Il est important que vous terminiez la rubrique suivante, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">change Voice routes to use the New Lync server 2013 Mediation Server</A> pour vous assurer que les itinéraires des communications vocales pointent vers le serveur de médiation approprié.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

