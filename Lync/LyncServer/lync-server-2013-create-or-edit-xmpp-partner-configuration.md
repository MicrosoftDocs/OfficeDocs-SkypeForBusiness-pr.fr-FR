---
title: 'Lync Server 2013 : création ou modification d’une configuration de partenaire XMPP'
description: 'Lync Server 2013 : création ou modification d’une configuration de partenaire XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553870"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Créer ou modifier la configuration d’un partenaire XMPP dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-03_

Microsoft Lync Server 2013 intègre un proxy XMPP (extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Pour autoriser les connexions à partir d’autres déploiements XMPP, vous devez configurer XMPP dans le panneau de configuration Lync Server. Vous configurez les paramètres sur un domaine XMPP. Pour créer une association de partenaires, procédez comme suit :

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Pour créer un nouveau partenaire fédéré ou modifier une configuration existante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **partenaires fédérés XMPP**.

4.  Pour créer une nouvelle configuration, cliquez sur **nouveau**

5.  Pour modifier une configuration existante, sélectionnez-la, puis cliquez sur **modifier** .

6.  Pour créer ou modifier des configurations pour des **partenaires fédérés XMPP**, vous devez définir les paramètres suivants :

7.  **Domaine principal** (obligatoire). Le domaine principal correspond au domaine de base du partenaire XMPP. Par exemple, vous pouvez entrer **fabrikam.com** comme nom de domaine du partenaire XMPP. Cette entrée est obligatoire.

8.  **Description**. La description correspond aux commentaires ou autres informations d’identification de la configuration particulière. Cette entrée est facultative.

9.  **Domaines supplémentaires**. Les domaines supplémentaires sont des domaines qui font partie du domaine de votre partenaire XMPP qui doivent être inclus dans le cadre de la communication XMPP autorisée. Par exemple, si le domaine principal est **fabrikam.com**, vous devez répertorier tous les autres domaines sous fabrikam.com que vous communiquez avec par le biais de XMPP. Par exemple, vous pouvez entrer **Corp.fabrikam.com** et **it.fabrikam.com** pour le domaine XMPP d’entreprise et le domaine XMPP de l’information technologies sous le domaine XMPP principal de fabrikam. com.

10. **Type de partenaire**. Le **type de partenaire** est un paramètre obligatoire et vous offre une sélection de trois choix dans un menu déroulant. Vous devez choisir l’une des options suivantes pour décrire et appliquer les contacts pouvant être ajoutés. Vous pouvez sélectionner l’une des options suivantes :
    
      - **Fédéré**. Un type de partenaire **fédéré** est une connexion approuvée entre un déploiement de partenaire Lync Server ou Office Communications Server 2007 R2.
    
      - **Public vérifié**. Un partenaire **vérifié public** se trouve lorsque les contacts qui font partie d’un déploiement vérifiés par le fournisseur peuvent être ajoutés à la liste des contacts de l’utilisateur. Les invitations peuvent être envoyées à partir de l’utilisateur Lync ou l’utilisateur Lync peut accepter des invitations du contact partenaire.
    
      - **Public non vérifié**. Une relation **publique non vérifiée** implique qu’il n’existe aucun État établi et vérifiable entre les deux déploiements. Un utilisateur Lync doit inviter le contact non vérifié pour ce contact à pouvoir ajouter l’utilisateur Lync à sa liste de contacts. Par exemple, Google GTalk n’est pas un service XMPP vérifié public, car il est lié à Lync Server. Un utilisateur GTalk ne pourra pas ajouter l’utilisateur Lync en tant que contact, sauf s’il existe une invitation explicite envoyée par l’utilisateur Lync.

11. Remarques sur la négociation de flux et les méthodes de sécurité protocole TLS (Transport Layer Security) et SASL (Software Authentication and Security Layer) :
    
    Le fichier xsf ( **XMPP Standards Foundation** ) et l’IETF ( **Internet Engineering Task Force** ) définissent un ensemble de règles et de normes pour l’utilisation et la gestion des certificats clients TLS, des certificats de serveur TLS et du mécanisme SASL. L’utilisation de TLS et de SASL est le processus requis pour sécuriser le flux XMPP. À partir du document de normes XMPP **XEP-0178**, spécifie un flux de protocole recommandé pour l’utilisation du mécanisme externe SASL avec des certificats PKIX, en particulier lorsqu’un service XMPP indique que TLS est obligatoire pour la négociation. PKIX, comme indiqué dans la documentation XSF, fait référence à l’infrastructure à clé publique, également appelée PKI.
    
    Reportez-vous au document XSF XEP-0178 pour plus d’informations sur les exigences XMPP. Pour plus d’informations, reportez-vous à la rubrique « XEP-0178 : meilleures pratiques pour l’utilisation d’SASL avec des certificats ». <http://xmpp.org/extensions/xep-0178.html>
    
    Reportez-vous au document IETF « extensible Messaging and Presence Protocol (XMPP) : Core », section 5,0, négociation STARTTLS <https://tools.ietf.org/html/rfc6120> .
    
      - **Négociation TLS**. Définit les règles de négociation TLS. Un service XMPP peut nécessiter TLS, peut rendre TLS facultatif ou vous pouvez décider de ne pas prendre en charge TLS. Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire. Pour afficher tous les paramètres et détails possibles pour la négociation SASL, TLS et rappel, y compris les configurations d’erreur connues et non valides-voir [paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obligatoire**. Le service XMPP nécessite la négociation TLS.
        
          - <span></span>  
            **Facultatif**. Le service XMPP indique que TLS est obligatoire pour la négociation.
        
          - <span></span>  
            **Non pris en charge**. Le service XMPP ne prend pas en charge TLS.
    
      - **Négociation SASL**. Définit les règles de négociation SASL. Un service XMPP peut nécessiter SASL, peut rendre SASL facultatif ou vous pouvez décider de ne pas prendre en charge SASL. Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.
        
        <div>
        

        > [!WARNING]  
        > SASL requiert TLS. Pour utiliser SASL, TLS doit être obligatoire ou facultatif. Toute configuration qui définit SASL, obligatoire ou facultatif, doit prendre en charge le protocole TLS. Lorsque vous cliquez sur <STRONG>valider</STRONG> pour enregistrer vos modifications, si vous n’avez pas défini TLS sur obligatoire ou facultatif, un avertissement s’affiche pour vous avertir que SASL doit être pris en charge par TLS et que vos modifications ne sont pas enregistrées. Pour résoudre l’erreur, définissez TLS sur <STRONG>obligatoire</STRONG> ou <STRONG>facultatif</STRONG>. Si l’utilisation de SASL est facultative et que la prise en charge de la négociation TLS n’est pas possible, vous devez définir la négociation SASL sur <STRONG>non pris en charge</STRONG>. Vérifiez auprès du service XMPP les flux de négociation corrects à utiliser pour TLS et SASL ou l’interruption de service.

        
        </div>
        
          - <span></span>  
            **Obligatoire**. Le service XMPP nécessite la négociation SASL.
        
          - <span></span>  
            **Facultatif**. Le service XMPP indique que SASL est obligatoire pour la négociation.
        
          - <span></span>  
            **Non pris en charge**. Le service XMPP ne prend pas en charge SASL.
    
      - **Négociation rappel**. La négociation rappel est définie par le fichier XSF dans le document **XEP-220 : Server rappel** <http://xmpp.org/extensions/xep-0220.html> . Le processus serveur rappel utilise le système DNS (Domain Name System) et un serveur faisant autorité pour vérifier que la demande provenait d’un partenaire XMPP valide. Pour ce faire, le serveur d’origine crée un message d’un type spécifique avec une clé rappel générée et recherche le serveur de réception dans le système DNS. Le serveur d’origine envoie la clé dans un flux XML à la recherche DNS résultante, vraisemblablement le serveur de réception. Lors de la réception de la clé sur le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur faisant autorité connu. Le serveur faisant autorité vérifie que la clé est valide ou non valide. S’il n’est pas valide, le serveur de réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur de réception informe le serveur d’origine que l’identité et la clé sont valides et que la conversation peut commencer.
        
        Il existe deux états valides pour la **négociation de rappel** :
        
          - <span></span>  
            **True**. Le serveur XMPP est configuré pour utiliser la négociation rappel si une demande doit être reçue d’un serveur d’origine
        
          - <span></span>  
            **False**. Le serveur XMPP n’est pas configuré pour utiliser la négociation rappel et si une demande doit être reçue d’un serveur d’origine, elle sera ignorée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

