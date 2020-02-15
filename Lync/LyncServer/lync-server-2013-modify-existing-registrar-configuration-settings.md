---
title: 'Lync Server 2013 : modifier les paramètres de configuration d’un serveur d’inscriptions existant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d7297ed0df352090f08b90475778f1bde788c8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Modifier les paramètres de configuration du serveur d’inscriptions existants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Vous pouvez utiliser le serveur d’inscriptions pour configurer les protocoles d’authentification du serveur proxy. Pour plus d’informations sur les protocoles disponibles, voir [créer des paramètres de configuration du serveur d’inscriptions dans Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

<div>


> [!NOTE]  
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.



</div>

Procédez comme suit pour modifier un serveur d’inscription existant.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>Pour modifier les paramètres de configuration d’un serveur d’inscriptions existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Dans la page **Serveur d’inscriptions**, cliquez sur un service, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier le paramètre du serveur d’inscriptions**, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
      - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
      - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

