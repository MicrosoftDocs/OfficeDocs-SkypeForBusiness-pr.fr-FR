---
title: 'Lync Server 2013 : création des paramètres de configuration du serveur d’inscriptions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2baa4cd40ae0f6421dbb01facecf0ab41825fc31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501591"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Créer des paramètres de configuration du serveur d’inscriptions dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-17_

Vous pouvez utiliser le serveur d’inscriptions pour configurer les méthodes d’authentification de serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de défis que les serveurs du pool émettent sur les clients. Les protocoles disponibles sont les suivants :

  - **Kerberos**     Il s’agit du modèle d’authentification par mot de passe le plus puissant disponible pour les clients, mais il est normalement disponible uniquement pour les clients d’entreprise, car il nécessite une connexion client à un centre de distribution de clés (contrôleur de domaine Kerberos). Ce paramètre est approprié si le serveur authentifie uniquement les clients d’entreprise.

  - **NTLM**     Il s’agit de l’authentification par mot de passe disponible pour les clients qui utilisent un modèle de hachage Challenge-Response sur le mot de passe. Il s’agit de la seule forme d’authentification disponible pour les clients sans connexion à un centre de distribution de clés (contrôleur de domaine Kerberos), comme les utilisateurs distants. Si un serveur authentifie uniquement les utilisateurs distants, vous devez choisir NTLM.

  - **Authentification par certificat**     Il s’agit de la nouvelle méthode d’authentification quand le serveur doit obtenir des certificats à partir de clients Lync Phone Edition, de téléphones de zone commune, de Lync 2013 et de l’application Lync Windows Store. Sur les clients Lync Phone Edition, une fois qu’un utilisateur s’est connecté et qu’il est authentifié à l’aide d’un code confidentiel (PIN), Lync Server 2013 met en service l’URI SIP pour le téléphone et procède à la mise en service d’un certificat signé Lync Server ou d’un certificat utilisateur qui identifie Joe (par exemple : SN=joe@contoso.com) sur le téléphone. Ce certificat est utilisé pour l’authentification auprès du serveur d’inscriptions et des services Web.

<div>


> [!NOTE]  
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.<BR>Si vous utilisez des clients d’application Lync Windows Store, vous devez activer l’authentification par certificat.



</div>

Procédez comme suit pour créer un serveur d’inscriptions.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Pour créer des paramètres de configuration du serveur d’inscriptions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Sur la page serveur d' **inscriptions** , cliquez sur **nouveau**

5.  Dans **Sélectionner un service**, cliquez sur le service auquel le serveur d’inscriptions doit s’appliquer, puis cliquez sur **OK**.

6.  Dans **paramètre nouveau**serveur d’inscriptions, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge dans votre environnement :
    
      - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
      - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

