---
title: 'Lync Server 2013 : configuration d’un nouveau serveur d’applications approuvées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e053629eae42bc7fcd83b0002b3aad40f3550f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507711"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Configurer un nouveau serveur d’applications approuvées dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Une application approuvée est une application basée sur Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK approuvé par Microsoft Lync Server 2013. Pour plus d’informations sur les applications UCMA, voir «documentation du kit de développement logiciel (SDK) Unified Communications Managed API 3,0 [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .

Pour plus d’informations sur la configuration de Microsoft Outlook Web Access (OWA) et de Lync Server 2013, voir « Configurer l’intégration d’Outlook Web App et de Lync Server 2010 » dans la documentation de Microsoft Exchange Server 2013.

Pour publier, activer ou désactiver correctement une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour l’ajout de rôles de serveur. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement. Pour procéder à d’autres modifications de la configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Pour configurer un serveur d’applications approuvées

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **enregistrer la topologie sous** , cliquez sur le fichier du générateur de topologies que vous souhaitez utiliser, puis cliquez sur **Enregistrer**.

5.  Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications approuvées**, puis cliquez sur **nouveau pool d’applications approuvées**.

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Lync Server 2013**, puis, dans le menu **actions** , cliquez sur **publier la topologie**.
    
    Le **pool d’applications approuvées** doit avoir été créé avec succès et associé au pool frontal correct.

</div>

</div>

<span> </span>

</div>

</div>

</div>

