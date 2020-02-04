---
title: 'Lync Server 2013 : Configuration des paramètres des comptes d’utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b74056587a192ec81f0dffb0044fb76e7698960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés. L’URI de **ligne** téléphonique spécifié sur les comptes d’utilisateurs de Lync Server est requis pour l’authentification.

La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un compte utilisateur unique. Si vous devez attribuer un **URI de ligne** à plusieurs comptes utilisateur, vous pouvez créer un script à l’aide de l’applet de commande **Set-CsUser**. Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer un **URI de ligne** à plusieurs comptes d’utilisateur, voir « [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)attribuer des URI de ligne à plusieurs utilisateurs ».

<div>

## <a name="to-configure-user-account-settings"></a>Pour configurer les paramètres de compte d’utilisateur

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.

5.  Double-cliquez sur le nom d’utilisateur pour ouvrir la boîte de dialogue **modifier l’utilisateur de Lync Server** .

6.  Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez spécifier un <STRONG>URI de ligne</STRONG> uniquement si l’option <STRONG>Téléphonie</STRONG> est définie sur <STRONG>De PC à PC uniquement</STRONG>, <STRONG>Voix Entreprise</STRONG>, <STRONG>Contrôle d’appel distant</STRONG> ou <STRONG>Contrôle d’appel distant uniquement</STRONG>.

    
    </div>

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

