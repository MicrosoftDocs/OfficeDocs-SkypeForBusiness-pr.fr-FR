---
title: Publication d’Office Web Apps Server avec un serveur proxy inverse
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Publication d’Office Web Apps Server dans Lync Server 2013 à l’aide d’un serveur proxy inverse

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent à partir de l’extérieur du pare-feu de votre organisation) puissent accéder aux présentations PowerPoint sur Office Web Apps Server, vous devrez utiliser Office Web Apps Server et un serveur proxy inverse tel que Microsoft Forefront Passerelle de gestion des menaces. Par ailleurs, vous devrez créer et configurer une règle de publication de site Web. Cette règle permet de garantir que les utilisateurs sont en mesure de se connecter au serveur. Si vous n’avez pas besoin de fournir un accès aux utilisateurs externes, vous n’avez pas besoin de configurer une règle de publication de site Web.

Pour configurer une règle de publication sur un site Web dans la passerelle gestion des menaces de Forefront, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Forefront TMG**, puis sur gestion de **Forefront TMG**.

2.  Dans Forefront TMG, cliquez avec le bouton droit sur **stratégie de pare-feu**, pointez sur **nouveau**, puis cliquez sur **règle de publication de site Web**.

3.  Dans l’Assistant Nouvelle règle de publication Web, dans la page **Bienvenue dans l’Assistant Nouvelle règle de publication Web** , tapez un nom pour votre nouvelle règle dans la zone nom de la **règle de publication Web** (par exemple, **Office Web Apps Server Rule**), puis cliquez sur **suivant**.

4.  Dans la page **spécifier une action de règle** , sélectionnez **autoriser** , puis cliquez sur **suivant**.

5.  Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge** , puis cliquez sur **suivant**.

6.  Dans la page sécurité de la **connexion au serveur** , sélectionnez **utiliser SSL pour se connecter au serveur Web ou à la batterie** de serveurs publié, puis cliquez sur **suivant**.

7.  Dans la page Détails de la **publication interne** , tapez le nom de domaine complet (FQDN) de votre serveur Office Web Apps (par exemple, **officewebapps01.contoso.com**) dans la zone **nom du site interne** , puis cliquez sur **suivant**. Le nom entré dans la zone **nom du site interne** doit apparaître dans le champ objet ou le champ autre nom de l’objet du certificat que vous avez attribué à Office Web Apps Server.

8.  Dans la page Détails de la **publication interne** , entrez ** / ** le **chemin d’accès (facultatif)** , puis cliquez sur **suivant**. La\* syntaxe permet de s’assurer que tous les dossiers et sous-dossiers du site sont publiés.

9.  Dans la page **Détails du nom public** , sélectionnez **ce nom de domaine (tapez ci-dessous)** dans la liste déroulante **accepter les demandes pour** et tapez le nom complet de votre serveur Office Web Apps dans la zone Nom du public. Ce nom doit être le nom utilisé pour accéder à votre site Web. Par exemple, si vous accédez à votre site à l' http://officewebapps01.contoso.com aide de l’URL, entrez **officewebapps01.contoso.com** dans la zone **nom du public** .

10. Cliquez sur **Suivant**.

11. Dans la page **Sélectionner un écouteur Web** , cliquez sur **nouveau**.

12. Dans l’Assistant Nouvelle définition de l’écouteur Web, tapez un nom pour le nouvel écouteur Web (par exemple, **SSL**) dans la zone nom de l' **écouteur Web** , puis cliquez sur **suivant**.

13. Dans la page **sécurité de connexion client** , sélectionnez **exiger des connexions SSL sécurisées avec les clients** , puis cliquez sur **suivant**.

14. Dans la page **adresses IP de l’écouteur Web** , sélectionnez **externe**, sélectionnez **interne**, puis cliquez sur **suivant**.

15. Sur la page **certificats SSL de l’écouteur** , sélectionnez **utiliser un certificat unique pour ce détecteur de site Web** , puis cliquez sur **Sélectionner un certificat**.

16. Dans la boîte de dialogue **Sélectionner un certificat** , sélectionnez le certificat que vous voulez utiliser pour ce détecteur Web, puis cliquez sur **Sélectionner**.

17. Sur la page **certificats SSL de l’écouteur** , cliquez sur **suivant**.

18. Dans la page **paramètres d’authentification** , sélectionnez **aucune authentification** dans la liste déroulante **Sélectionner la façon dont les clients fournissent des informations d’identification à l’aide de la liste déroulante Sélectionner la façon dont les clients doivent fournir des informations d’identification à** la ****

19. Dans la page **paramètres de connexion unique** , cliquez sur **suivant**.

20. Dans la page **fin de l’Assistant Nouvelle écoute Web** , consultez le résumé des choix de configuration que vous avez effectués. Lorsque vous êtes prêt, cliquez sur **Terminer**.

21. Dans la page **Sélectionner un écouteur Web** , cliquez sur **suivant**.

22. Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, mais le client pourra s’authentifier directement** dans la liste déroulante **Sélectionner la méthode utilisée par Forefront TMG pour s’authentifier dans la** liste déroulante du serveur Web publié, puis cliquez sur **suivant**.

23. Dans la page **ensembles d’utilisateurs** , vérifiez que les jeux d’utilisateurs appropriés apparaissent. Par défaut, il s’agit de l’utilisateur **tous les utilisateurs** définis. Cliquez sur **Ajouter** pour ajouter d’autres jeux d’utilisateurs que vous avez éventuellement définis. Lorsque vous avez terminé, cliquez sur **suivant**.

24. Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , cliquez sur **Terminer**.

Notez que le fait de cliquer sur **Terminer** ne signifie pas que vous avez terminé le processus. c’est-à-dire qu’elle n’est pas appliquée automatiquement et qu’elle est activée. À la place, vous devrez cliquer sur le bouton **appliquer** qui s’affichera dans l’interface utilisateur de Forefront TMG. Lorsque vous cliquez sur **appliquer** , la boîte de dialogue Description de la **modification de configuration** s’affiche. Dans cette boîte de dialogue, cliquez sur **appliquer** pour activer la nouvelle règle de publication.

Une fois votre nouvelle règle appliquée, vous devrez apporter quelques modifications mineures à la règle pour vous assurer que les utilisateurs peuvent utiliser les nouvelles fonctionnalités de présentation PowerPoint. Pour cela, procédez comme suit :

1.  Dans Forefront TMG, cliquez avec le bouton droit sur le nom de la nouvelle règle de publication, puis cliquez sur **Propriétés**.

2.  Dans la boîte de dialogue **Propriétés** , sous l’onglet **à** , sélectionnez l’option **transférer l’en-tête d’hôte d’origine au lieu de l’en-tête réel**.

3.  Dans l’onglet **trafic** , cliquez sur **filtrage** , puis sur **configurer http**.

4.  Dans la boîte de dialogue Configuration de la **stratégie http pour la règle** , décochez la case **Vérifier la normalisation** , puis cliquez sur **OK**.

5.  Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.

6.  Dans Forefront TMG, cliquez sur **appliquer** pour activer les modifications. Lorsque la boîte de dialogue Description de la modification de la **configuration** s’affiche, cliquez sur **appliquer**.

À l’issue de l’installation, vous pouvez tester votre serveur Office Web Apps en suivant les procédures décrites dans la rubrique [vérification de la configuration d’Office Web Apps Server dans Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

