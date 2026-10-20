# Project1
Lighting

"We received a DIALux report from another team and needed to check it properly. That meant more than checking that the lux levels passed. We also had to make sure each room was designed to the right target.

I wrote a Python script to pull out the room data and flag what met the criteria. Before using AI, I stripped out anything confidential.

AI then built this register. For every room, it confirmed what the space is actually used for. Then it checked three sources: EN 12464-1, the client's design guide and the basis of design. Where they disagreed, the most stringent requirement set the final lux and uniformity target, and every decision has a written justification.

Most importantly, it told me exactly which calculations to change and which to leave, so I only reworked what needed it.

That was about checking the design itself. The next tool checks what we actually issue."

DDI

"Before we issue drawings, someone has to go through the DDI line by line. They check that every drawing on it is in the issue folder, with the right reference and revision. On a big project that can mean hundreds of drawings. It's slow and repetitive, and it's easy to miss something.

So I built a tool that does it automatically. It reads every drawing reference from the DDI, scans the project folder and compares the two.

The code on the right is the core of it. For each drawing, it first standardises the reference so small formatting differences don't cause false mismatches. Then it searches the project files for that reference.

One match means it's matched. No match means it's missing. More than one means it's a duplicate. It also picks up any extra files that aren't on the DDI.

At the end, it produces a colour-coded Excel report with the status, revision and file location for every drawing, so you can see straight away what needs fixing.

Instead of spending hours checking by hand, we get a reliable QA report in seconds. The engineer's time goes on fixing issues, not finding them.

That tool checks documents. The next one actually builds them."

Schedules

"Buckingham needed the distribution board schedules in their own template, but Revit wouldn't let us export the schedules directly to Excel. Rebuilding every board by hand, circuit by circuit, would have taken ages and been easy to get wrong.

So we exported the raw schedule data instead, and I wrote a script in Google Sheets to rebuild them. It groups every circuit by its board, copies the template for each one and fills it in. It reads each circuit reference, works out which way and phase the circuit goes on, and marks the empty ways as spares.

It also checks its own work. If two circuits land in the same spot, a circuit goes beyond the board's ways, or old data from the template is left behind, it flags it instead of overwriting anything. Everything goes into a build log.

The first version was tied to Buckingham's template. I've since moved the template details into a config tab: rows, ways, phases, columns and header cells. That means it isn't a one-off. For a new project, you map the template once and run it.

What used to be hours of copying is now one click, and it can be rerun whenever the model changes.

All three of these tools automate one task at a time. The bigger opportunity is to automate the design itself."

Opportunities

"The longer-term idea is to move from automating individual tasks to an engineering design engine.

For lighting, the engine would learn design patterns from previous projects. It would combine those with defined engineering parameters and standards to generate a first-draft design.

A calculation layer then checks that design, so we're not relying on AI-generated values.

Claude acts as the interface. An engineer can question the design, ask for changes and look at suitable fittings.

The output would be the layout, calculations, schedules and a report, ready for engineering review or further checking in DIALux.

To start with, this is about getting a much faster first draft. Over time, the same setup could support more of the detailed design workflow.

So it goes from checking the design, to checking what we issue, to building our deliverables, and finally to helping produce the design itself."
