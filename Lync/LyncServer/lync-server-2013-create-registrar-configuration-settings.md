---
title: 'Lync Server 2013: créer des paramètres de configuration du Bureau d’enregistrement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Créer des paramètres de configuration du Bureau d’enregistrement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-17_

Vous pouvez utiliser le serveur d’inscriptions avancé pour configurer les méthodes d’authentification du serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de difficultés que les serveurs du pool posent aux clients. Les protocoles disponibles sont les suivants :

  - **Kerberos**   il s’agit du schéma d’authentification par mot de passe le plus puissant disponible pour les clients, mais uniquement pour les clients d’entreprise, car cela nécessite une connexion client à un centre de distribution de clés (contrôleur de domaine Kerberos). Ce paramètre est adapté si le serveur ne doit authentifier que des clients entreprise.

  - **NTLM**   il s’agit de l’authentification par mot de passe qui est disponible pour les clients qui utilisent un modèle de hachage de réponse à la demande du mot de passe. C’est la seule forme d’authentification proposée aux clients ne disposant pas d’une connectivité à un centre de distribution des clés (contrôleur de domaine Kerberos), comme les utilisateurs distants. Si un serveur n’authentifie que des utilisateurs distants, vous devez choisir NTLM.

  - **Authentification par**   certificat il s’agit de la nouvelle méthode d’authentification lorsque le serveur doit obtenir des certificats de clients Lync Phone Edition, de téléphones de zone commune, de Lync 2013 et de l’application Lync du Windows Store. Sur les clients Lync Phone Edition, une fois que l’utilisateur s’est connecté et est authentifié par le biais d’un code confidentiel (PIN), Lync Server 2013 configure l’URI SIP sur le téléphone et configure un certificat signé ou un certificat utilisateur Lync Server. qui identifie Joe (par exemple: SN=joe@contoso.com) sur le téléphone. This certificate is used for authenticating with the Registrar and Web Services.

<div>


> [!NOTE]  
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également sur le serveur, Kerberos est utilisé.<BR>Si vous allez utiliser les clients de l’application Lync du Windows Store, vous devez activer l’authentification par certificat.



</div>

Pour créer un serveur d’inscriptions avancé, procédez comme suit.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Pour créer des paramètres de configuration du serveur d’inscriptions avancé

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.

4.  Dans la page **Serveur d’inscriptions avancé**, cliquez sur **Nouveau**.

5.  Dans **Sélectionner un service**, cliquez sur le service auquel le serveur d’inscriptions avancé s’appliquera, puis cliquez sur **OK**.

6.  Dans **Nouveau paramètre de serveur d’inscriptions avancé**, sélectionnez un ou plusieurs des éléments ci-dessous selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
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

