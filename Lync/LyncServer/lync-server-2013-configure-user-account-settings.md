---
title: 'Lync Server 2013 : configuration des paramètres de compte d’utilisateur'
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
ms.openlocfilehash: 68681e172c4683a29bb676630250f7268e20fade
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Configurer les paramètres de compte d’utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés. L’URI de **ligne** de téléphonie spécifié sur les comptes d’utilisateur Lync Server est requis pour l’authentification.

La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un seul compte d’utilisateur. Si vous devez affecter un **URI de ligne** à plusieurs comptes d’utilisateur, vous pouvez créer un script qui utilise l’applet de commande **Set-CsUser**. Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer un **URI de ligne** à plusieurs comptes d’utilisateur, voir « [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)attribuer des URI de ligne à plusieurs utilisateurs » à l’adresse.

<div>

## <a name="to-configure-user-account-settings"></a>Pour configurer les paramètres des comptes d’utilisateur

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.

5.  Double-cliquez sur le nom d’utilisateur pour ouvrir la boîte de dialogue **modifier l’utilisateur Lync Server** .

6.  Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez spécifier l' <STRONG>URI de ligne</STRONG> uniquement si la <STRONG>téléphonie</STRONG> est définie sur <STRONG>PC à PC uniquement</STRONG>, <STRONG>voix entreprise</STRONG>, <STRONG>contrôle d’appel distant</STRONG> ou <STRONG>contrôle d’appel distant uniquement</STRONG>.

    
    </div>

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

