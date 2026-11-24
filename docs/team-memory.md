[← SailorBridge](../README.md)

# Team memory

Team memory keeps decisions, conventions, and fixes that your **Leader** and workers can use on later jobs. Each entry has a title, a body, a source, and a number such as `#6`. An entry belongs to one team. Other teams and friends cannot browse it.

## Record something worth keeping

In team chat, say what to remember and when it applies. For example, “Remember that installation examples belong in the setup guide. Use it when changing an install command.” The **Leader** tells you what it recorded. Open the team chat’s **More Actions** menu and choose **Team Memory** to see the entry. Open its title to read the full text and see who last changed it.

## Find an entry and use it in chat

Open **Search** in **Team Memory**. Enter words from the title or body. Every word must match for a text result, and the first page can also show up to three entries with similar meanings. Pinned entries appear first in the ordinary list.

If you know the number, search for `#6` to get only entry 6. Searching for `6` also finds text matches. Open the entry and choose **Go to Chat**. The input now contains `/memory #6`. Add a question or correction and send it.

## Edit, pin, lock, or delete an entry

- Open the entry, change **Body**, and choose **Save**. **History** shows the last 10 versions. Check **Observed** and **Expires** for facts that can change. An **Expired** entry stays readable, so check whether its advice still applies.
- Turn on **Pinned** to put an instruction in the material given to the **Leader** and workers. The entry shows the team’s pinned usage. All pinned titles and bodies together can use up to 8 KiB.
- Turn on **Locked** if only you should be able to change or delete it. Pinning alone still lets agents edit the entry. You can edit a locked entry on the web.
- Choose **Delete** and confirm to remove an entry permanently. Its number will not be reused.

## Tidy the team’s entries

Send `/memory-tidy` in team chat. The job checks entries, marks those worth keeping, merges related entries, and deletes ones with no future use. Open its **Delivery Report** to see what it did and what still needs your decision. Locked entries stay in place if the job proposes deleting or merging them.

Automatic tidying runs at most once per team in a rolling 24 hours when there are entries to check. To run it only when you ask or schedule it, open **Team Flows**, select `memory-tidy`, and turn off **Auto Tidy**.

## When it does not work

- A pin that would exceed 8 KiB is refused. Unpin another entry or shorten the pinned text, then try again.
- If someone edited the entry while you were working, the latest body appears. Read it before applying your correction again.
- If two updates use the same title, a correction from the same author can take effect directly. Otherwise a higher confirmation level, or a more recent observation at the same level, can settle it. If the updates need a decision, the entry shows **Unresolved Conflict** and keeps its current text. Open it, check the fact, and save the correct wording. A locked entry needs your decision.
- If the **Leader** reports that a memory was not saved, repeat what you want it to remember. If an agent was refused because the entry is locked, make the change yourself in **Team Memory**.
