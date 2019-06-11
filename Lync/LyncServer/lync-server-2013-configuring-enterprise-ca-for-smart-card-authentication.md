---
title: 'Lync Server 2013: configuration d’une autorité de certification d’entreprise pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-03_

La section suivante décrit comment configurer une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce. Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir installer une [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)autorité de certification racine d’entreprise à l’adresse.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce

La procédure ci-dessous décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :

1.  Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.

2.  Lancez le gestionnaire système, puis vérifiez que le rôle Inscription de l’autorité de certification par le biais du web est installé.

3.  Dans le menu **Outils d’administration**, ouvrez la console de gestion **Autorité de certification**.

4.  Dans le volet de navigation, développez **Autorité de certification**.

5.  Cliquez avec le bouton droit sur **Modèles de certificat**, sélectionnez **Nouveau**, puis **Modèle de certificat à délivrer**.

6.  Sélectionnez **Agent d’inscription**, **Utilisateur de carte à puce** et **Connexion par carte à puce**.

7.  Cliquez sur **OK**.

8.  Cliquez avec le bouton droit sur **Modèles de certificat**.

9.  Sélectionnez **Gérer**.

10. Ouvrez les propriétés du modèle utilisateur de carte à puce.

11. Cliquez sur l’onglet **Sécurité**.

12. Modifiez les autorisations, comme suit :
    
      - Ajoutez des comptes Active Directory d’utilisateurs individuels avec les autorisations Lire/Inscrire (Autoriser) ou
    
      - Ajoutez un groupe de sécurité contenant des utilisateurs de carte à puce avec les autorisations Lire/Inscrire (Autoriser) ou
    
      - Ajoutez le groupe Utilisateurs du domaine avec les autorisations Lire/Inscrire (Autoriser).

</div>

</div>

<span> </span>

</div>

</div>

</div>

