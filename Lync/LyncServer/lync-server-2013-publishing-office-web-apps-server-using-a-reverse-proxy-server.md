---
title: Publication d’Office Web Apps Server à l’aide d’un serveur proxy inverse
description: Publication d’Office Web Apps Server à l’aide d’un serveur proxy inverse.
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
ms.openlocfilehash: 888399e315d90624ba41e23e173fa33813a92b43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571730"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Publication d’Office Web Apps Server dans Lync Server 2013 à l’aide d’un serveur proxy inverse

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Si vous souhaitez que les utilisateurs externes (c’est-à-dire, les utilisateurs qui se connectent depuis l’extérieur du pare-feu de votre organisation) aient accès aux présentations PowerPoint d’Office Web Apps Server, vous devez utiliser Office Web Apps Server et un serveur de proxy inverse tel que Microsoft Forefront Threat Management Gateway. Cela signifie également que vous devrez créer et configurer une règle de publication de site Web ; Cette règle permet de s’assurer que les utilisateurs peuvent se connecter au serveur. Si vous n’avez pas besoin d’autoriser l’accès à des utilisateurs externes, vous n’avez pas besoin de configurer une telle règle.

Pour configurer une règle de publication de site web dans Forefront Threat Management Gateway, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Forefront TMG**, puis sur **Forefront TMG Management**.

2.  Dans Forefront TMG, cliquez avec le bouton droit sur **Stratégie de pare-feu**, pointez sur **Nouveau**, puis cliquez sur **Règle de publication de site web**.

3.  Dans l’Assistant Nouvelle règle de publication web, dans la page **Bienvenue dans l’Assistant Nouvelle règle de publication web**, tapez le nom de votre nouvelle règle dans la zone **Nom de la règle de publication web** (par exemple, **Règle Office Web Apps Server**), puis cliquez sur **Suivant**.

4.  Dans la page **Spécifier l’action de la règle**, sélectionnez **Autoriser**, puis cliquez sur **Suivant**.

5.  Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**, puis cliquez sur **Suivant**.

6.  Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**, puis cliquez sur **Suivant**.

7.  Dans la page **Détails de la publication interne**, tapez le nom de domaine complet du serveur Office Web Apps (par exemple, **officewebapps01.contoso.com**) dans la zone **Nom de site local**, puis cliquez sur **Suivant**. Le nom entré dans la zone **Nom de site local** doit figurer dans le champ Sujet ou le champ Autre nom du sujet du certificat que vous avez affecté à Office Web Apps Server.

8.  Sur la page **Détails de publication interne** , tapez **/\*** dans la zone **chemin d’accès (facultatif)** , puis cliquez sur **suivant**. La \* syntaxe permet de s’assurer que tous les dossiers et sous-dossiers du site sont publiés.

9.  Dans la page **Informations sur les noms publics**, sélectionnez **Ce nom de domaine (saisissez ci-dessous)** dans la zone déroulante **Accepter les demandes pour**, puis tapez le nom complet de votre serveur Office Web Apps Server dans la zone de nom public. Ce nom doit être le même que le nom utilisé pour accéder à votre site web. Par exemple, si vous accédez à votre site à l’aide de l’URL http://officewebapps01.contoso.com , entrez **officewebapps01.contoso.com** dans la zone **nom public** .

10. Cliquez sur **Suivant**.

11. Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Nouveau**.

12. Dans l’Assistant Nouvelle définition de port d’écoute web, tapez le nom du nouveau port d’écoute web (par exemple, **SSL**) dans la zone **Nom du port d’écoute web**, puis cliquez sur **Suivant**.

13. Dans la page **Sécurité de la connexion cliente**, sélectionnez **Exiger les connexions sécurisées SSL avec les clients**, puis cliquez sur **Suivant**.

14. Dans la page **Adresses IP des ports d’écoute web**, sélectionnez **Externe**, sélectionnez **Interne**, puis cliquez sur **Suivant**.

15. Dans la page **Certificats SSL du port d’écoute**, sélectionnez **Utiliser un seul certificat pour ce port d’écoute web**, puis cliquez sur **Sélectionner le certificat**.

16. Dans la boîte de dialogue **Sélectionner le certificat**, sélectionnez le certificat à utiliser pour ce port d’écoute web, puis cliquez sur **Sélectionner**.

17. Dans la page**Certificats SSL du port d’écoute**, cliquez sur **Suivant**.

18. Dans la page **Paramètres d’authentification**, sélectionnez **Aucune authentification** dans la liste déroulante **Sélectionner la méthode avec laquelle les clients fourniront les informations d’identification à Forefront TMG**, puis cliquez sur **Suivant**.

19. Dans la page **Paramètres de l’authentification unique**, cliquez sur **Suivant**.

20. Dans la page **Fin de l’Assistant Nouveau port d’écoute web**, vérifiez le résumé de vos choix de configuration. Lorsque c’est fait, cliquez sur **Terminer**.

21. Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Suivant**.

22. Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation, mais le client peut s’authentifier directement** dans la liste déroulante **Sélectionner la méthode utilisée par Forefront TMG pour s’authentifier auprès du serveur web publié**, puis cliquez sur **Suivant**.

23. Dans la page **Ensembles d’utilisateurs**, confirmez que les ensembles d’utilisateurs appropriés sont répertoriés. Par défaut, il s’agit de l’ensemble d’utilisateurs **Tous les utilisateurs**. Cliquez sur **Ajouter** pour ajouter les autres ensembles d’utilisateurs que vous avez éventuellement définis. Lorsque c’est fait, cliquez sur **Suivant**.

24. Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, cliquez sur **Terminer**.

Notez que le fait de cliquer sur **Terminer** ne signifie pas que vous avez terminé la procédure ; en d’autres termes, la nouvelle règle n’est pas automatiquement appliquée. En fait, vous devez cliquer sur le bouton **Appliquer** qui apparaît dans l’interface utilisateur de Forefront TMG. Lorsque vous cliquez sur **Appliquer**, la boîte de dialogue **Description de la modification de la configuration** s’affiche. Cliquez sur **Appliquer** dans cette boîte de dialogue pour activer la nouvelle règle de publication.

Une fois que votre nouvelle règle a été appliquée, vous devrez apporter quelques modifications mineures à la règle afin de garantir que les utilisateurs peuvent utiliser les nouvelles fonctionnalités de présentation PowerPoint. Pour cela, procédez comme suit :

1.  Dans Forefront TMG, cliquez avec le bouton droit sur le nom de la nouvelle règle de publication, puis cliquez sur **Propriétés**.

2.  Dans la boîte de dialogue **Propriétés**, sous l’onglet **À**, sélectionnez l’option **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel**.

3.  Sous l’onglet **Trafic**, cliquez sur **Filtrage**, puis sur **Configurer HTTP**.

4.  Dans la boîte de dialogue **Configuration de la stratégie HTTP pour la règle**, désactivez la case à cocher **Vérifier la normalisation**, puis cliquez sur **OK**.

5.  Dans la boîte de dialogue **Propriétés**, cliquez sur **OK**.

6.  Dans Forefront TMG, cliquez sur **Appliquer** pour appliquer les modifications. Lorsque la boîte de dialogue **Description de la modification de la configuration** s’affiche, cliquez sur **Appliquer**.

Une fois l’installation terminée, vous pouvez tester votre serveur Office Web Apps Server à l’aide des procédures décrites dans la rubrique [validation de la configuration d’Office Web Apps Server dans Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

