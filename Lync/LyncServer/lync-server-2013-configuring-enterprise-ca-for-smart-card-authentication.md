---
title: 'Lync Server 2013 : configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 315d98e26b471e2d9dd84dcb70cd7302e924e9b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

La section suivante décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce. Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, consultez la rubrique [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364)installer une autorité de certification racine d’entreprise à l’adresse.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce

Les étapes suivantes décrivent comment configurer une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :

1.  Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.

2.  Lancez le Gestionnaire système et assurez-vous que le rôle d’inscriptions par le Web de l’autorité de certification est installé.

3.  Dans le menu **Outils d’administration** , ouvrez la console de gestion **autorité de certification** .

4.  Dans le volet de navigation, développez **autorité de certification**.

5.  Cliquez avec le bouton droit sur **modèles de certificats**, sélectionnez **nouveau**, puis **modèle de certificat à délivrer**.

6.  Sélectionnez **agent d’enregistrement**, **utilisateur de carte à puce**et ouverture de session par carte à **puce**.

7.  Cliquez sur **OK**.

8.  Cliquez avec le bouton droit sur **modèles de certificats**.

9.  Sélectionnez **gérer**.

10. Ouvrez les propriétés du modèle utilisateur SmartCard.

11. Cliquez sur l’onglet **sécurité** .

12. Modifiez les autorisations comme suit :
    
      - Ajouter des comptes AD d’utilisateur individuels avec des autorisations Lecture/inscription (autoriser) ou
    
      - Ajouter un groupe de sécurité contenant des utilisateurs de carte à puce avec des autorisations Lecture/inscription (autoriser) ou
    
      - Ajouter le groupe utilisateurs du domaine avec les autorisations lire/inscrire (autoriser)

</div>

</div>

<span> </span>

</div>

</div>

</div>

