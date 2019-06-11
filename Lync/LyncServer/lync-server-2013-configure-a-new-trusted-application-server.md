---
title: 'Lync Server 2013: configurer un nouveau serveur d’applications de confiance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurer un nouveau serveur d’applications de confiance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Microsoft Lync Server 2013. Pour plus d’informations sur les applications UCMA, voir la documentation relative au kit de développement logiciel [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)unifié API 3,0 principal du SDK.

Pour plus d’informations sur la configuration de Microsoft Outlook Web Access (OWA) et de Lync Server 2013, voir «configurer Outlook Web App et intégration de Lync Server 2010» dans la documentation Microsoft Exchange Server 2013.

Pour la publication, l’activation ou la désactivation d’une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les autorisations et les droits d’administrateur appropriés pour ajouter des rôles de serveur. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement. Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Pour configurer un serveur d’applications de confiance

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

3.  Sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **enregistrer la topologie comme** , cliquez sur le fichier de générateur de topologie que vous voulez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance**, puis cliquez sur **nouveau pool d’applications approuvés**.

6.  Entrez le **nom de domaine complet (FQDN** ) du pool d’applications de confiance, puis choisissez s’il s’agit d’un serveur unique ou d’un serveur, puis cliquez sur **suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal de Lync Server 2013.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Lync Server 2013**, puis dans le menu **actions** , cliquez sur **publier la topologie**.
    
    Le **pool d’applications approuvé** doit avoir été créé avec succès et associé au pool frontal approprié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

